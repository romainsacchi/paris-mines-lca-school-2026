# Course Adaptation Questions

This file is meant to be answered inline. The goal is to decide how to adapt this repository from the Barcelona regionalised LCIA course into the new Mines Paris - PSL doctoral training described in `offer_19.docx`.

Known from the offer:

- Format: in-person, Paris
- Dates: May 4-7, 2026
- Audience: doctoral students and researchers from the Laboratoire Recherche Environnement, Mines Paris - PSL
- Duration: 4 days, 28 hours
- Indicative split:
  - 1.5 days Brightway 2.5
  - 0.5 day Activity Browser
  - 1 day Premise
  - 0.5 day Edges
  - 0.5 day Trails / dynamic LCA, if group progress allows
- Instructors: Romain Sacchi as main instructor; Bernhard Steubing for Activity Browser modules

## 1. Course Identity

1. What should the public course title be?

Answer: Doctoral training: LCA with Brightway2.5, Premise and Edges

2. Should the course material be written in English, French, or mixed language?

Answer: English

3. Should the repository name/slug and internal Brightway project name be changed? For example, from `barcelona-rlcia-2026` to `mines-paris-lca-2026`.

Answer: Yes

4. Should the README mention the exact dates and location, or keep the material more reusable/generic?

Answer: the README should mention the exact dates and location

5. Should Bernhard Steubing be listed in the public README and schedule, or only in internal notes / Activity Browser sections?

Answer: Bernhard Steubing should be listed in the public README and schedule. 
However, he will be instructing only for the Activity Browser modules, while Romain Sacchi will be the main instructor for the other modules. 
The README and schedule should reflect this division of instruction clearly, so participants know which instructor to expect for each part of the course. 


## 2. Audience And Prerequisites

6. What Python level should I assume: complete beginners, basic notebook users, or intermediate scientific Python users?

Answer: -	Basic knowledge of Python programming, this is why we point also to a Python tutorial in the README.

7. Should we keep a Python/Jupyter refresher notebook?

Answer: Yes, we should keep a Python/Jupyter refresher notebook.
This will help ensure that all participants, regardless of their prior experience with Python and Jupyter, have a common foundation to build upon during the course. 
The refresher notebook can cover essential Python concepts, Jupyter notebook usage, and any specific libraries or tools that will be used throughout the course. 
This will help participants feel more confident and prepared for the hands-on exercises and activities that will be part of the course, ultimately enhancing their learning experience and engagement with the material.

8. How much prior LCA knowledge should the material assume?

Answer: We should assume the participants have a good understanding of LCA concepts, as they are doctoral students and researchers in the field.
The course can focus more on the application of LCA using Brightway, Premise, and Edges, rather than covering basic LCA principles. 


9. Is the group expected to install everything before the course, or should time be reserved on Day 1 for installation help?

Answer: The participants will have followed the instructions before the course and they have a couple of weeks before the course to contact me if they have any issues with the installation.

10. Maximum expected participant count is 20 in the offer. Is that still correct?

Answer: Yes

## 3. Database Strategy

11. Should the course use the bundled open BAFU database for Brightway exercises?

Answer: For teh Brightway exercises, which will extend over a day and a half, yes. At the end of that module, and before the forst Activity-Browser part, we will import Ecoinvent, as we will need it for the Activity Browser part and teh Premise part too.

12. Will participants have access to `ecoinvent`?

Answer: I think so, but I am not certain. For that reason, I would like to keep the course runnable without `ecoinvent`, but also include `ecoinvent` import and use as an optional part for those who have access, and import it at the end of the brightway module.

13. If yes, which `ecoinvent` version should the course target?

Answer: 3.12 cutoff, but I will check with the lab to confirm which version they have access to.

14. Should the repository remain runnable without `ecoinvent`, with `ecoinvent` workflows shown as optional/demo material?

Answer: We will keep the brightway and edges modules runnable witht eh BAFU database. And teh Premise and Activity Browser and Trails modules will run with ecoinvent.

15. For Premise, should participants generate Premise databases during the course, or should we provide/use pre-generated outputs?

Answer: They will generate the databases during the course.

16. If participants will generate Premise databases, what source database, model, pathway, and target years should be used?

Answer: We will use ecoinvent 3.12 cutoff as the source database, and we will use REMIND-EU as the model, and the SSP2-NPi and the SSP2-PkBudg1000 scenarios. We will cover the years 2025, 2035, and 2050.

17. Are there any licensing or data-sharing constraints that should be stated explicitly in the README and setup instructions?

Answer: No, besodes those already contained concerning the BAFU database. And also that some modules will rely on the ecoinvent database, which we do nto provide and we ask teh participants to obtain ecoinvent credentials to log in to ecoinvent.org.

## 4. Environment Strategy

18. Should there be one unified conda environment for the whole course, or separate environments for Brightway/Activity Browser and Premise?

Answer: I htink it should be possible to have brightway 2.5, edges, premise and trails in one environment. Activity Browser cna be pip-installed, as the current conda recipes reflect. We can remove the other conda recipes.

19. The current `bw` environment includes Activity Browser and Edges. The current `premise` environment pins older Brightway packages. Should I modernize/consolidate these environments, or leave them separate?

Answer: We should only use the `bw` environment, which we can rename to `lca-course` or something like that. We can remove the `premise` environment, and we can update the `bw` environment to include the latest versions of brightway, edges, and premise. We can also include the Activity Browser pip installation in the same environment, as it is compatible with the latest brightway version.

20. Which operating systems should be supported in the setup instructions: Windows, macOS Apple Silicon, macOS Intel, Linux?

Answer: Windows, macOS Apple Silicon, Linux

21. Should Activity Browser be installed through the same course environment, or should participants use a separate Activity Browser installer/environment?

Answer: We can install Activity Browser through the same course environment, as it is compatible with the latest brightway version. This will simplify the setup process for participants, as they will only need to manage one environment for the entire course. We can include the pip installation command for Activity Browser in the same environment YAML file, so that participants can easily install it along with the other necessary packages.

22. Is internet access during the course reliable enough for downloads/API calls, or should notebooks be made as offline as possible?

Answer: Yes, internet access during the course is expected to be reliable enough for downloads and API calls. However, we should still aim to make the notebooks as offline-friendly as possible, by including any necessary data files in the repository and minimizing reliance on external resources that may be subject to connectivity issues.

## 5. Brightway Module - 1.5 Days

23. Which current Day 1 notebooks should stay in the active course path?

Suggested current notebooks:

- `D1-01 Python and Jupyter minimum refresher`
- `D1-02 Brightway architecture and data model`
- `D1-03 Manual LCA with NumPy matrices`
- `D1-04 First LCA from demand to score in Brightway`
- `D1-05 Uncertainty and Monte Carlo basics`
- `D1-06 Data quality checks and linking workflow`
- `D1-07 Contribution analysis and result visualization`

Answer: They all belong to DAY 1. Then, half a day on DAY 2 can be spent to import ecoinvent and explore it and quickly revisit concepts we saw with the BAFU database on DAY 1, until noon of DAY 2. Then, the afternoon of DAY 2 can be dedicated to the Activity Browser.

24. Should the Brightway section prioritize conceptual understanding, hands-on model building, database import, or analysis workflows?

Answer: I think we can preserve the current structure and content.

25. Should matrix notation / Heijungs and Suh stay as a full notebook, a short explanation, or be removed?

Answer: No, we should preserve teh current content.

26. Should uncertainty and Monte Carlo be taught in Brightway, Activity Browser, or both?

Answer: Both

27. Should global sensitivity analysis (GSA) be covered in code, in Activity Browser, or only conceptually?

Answer: in Activity Browser

28. Should contribution analysis and visualization stay in the Brightway part?

Answer: Yes

29. Should the data QA/linking/parameters notebook stay, given the limited 1.5-day Brightway allocation?

Answer: Yes

## 6. Activity Browser Module - 0.5 Day

30. Should Activity Browser material be notebook-based, slide/demo notes, screenshots, or a short lab handout?

Answer: Activity Browser is a GUI tool, so it is not well-suited for notebook-based exercises. Instead, we can prepare a short lab handout with step-by-step instructions and screenshots to guide participants through the Activity Browser workflows. This will allow them to follow along and explore the tool at their own pace during the 0.5-day allocation.

31. Which Activity Browser workflows should be included before the Premise module?

Possible workflows:

- opening the project/database created in Brightway
- inspecting activities and exchanges
- running LCAs
- parameterization
- Monte Carlo
- GSA
- contribution analysis / visualization

Answer: The Activity Browser section will be divided into two parts: the first module, following the Brightway module, will focus in particular on advanced features such as parameterisation, Monte Carlo simulations and GSA

32. Which Activity Browser workflows should be included after the Premise module?

Possible workflows:

- importing Premise-generated databases
- comparing scenarios
- comparing years
- comparing technologies
- exporting plots/results

Answer: the second Activity Browser module will be dedicated to the Premise-generated databases, and we will focus on comparing scenarios, years and technologies, and also on exporting plots and results.

33. Do you already have Activity Browser screenshots or teaching material to reuse?

Answer: not yet

## 7. Premise Module - 1 Day

34. What should be the learning goals for the Premise day?

Answer: there will be a presentation for about one hour, explaining the role of IAM models, scenarios, etc. THen, the participants will learn how to compare scenario narratives. Then, they will learn how to use Premise ot generate prospective LCA databases, to be imported in Brightway/Activity Browser. Then, they will learn how to compare scenarios, years and technologies in Activity Browser in the second Activity Browser module.

35. Which scenario framework should be used? For example, REMIND, IMAGE, IAMC scenario names, SSP/RCP combinations, etc.

Answer: We will likely focus on REMIND-EU (a Europe-focused version of REMIND), comparing the SSP2 socioeconomic pathways across two climate policies: NPi and PkBudg1000.

36. Which years should be covered?

Answer: We will cover the years 2025, 2035 and 2050.

37. Which sectors should be emphasized? For example electricity, transport, cement, steel, fuels, hydrogen, vehicles.

Answer: We will integrate all teh sectors Premise is able to model, but we will likely put a particular emphasis on the electricity sector.

38. Should the Premise exercises focus on generating databases, inspecting changes, running LCAs, or integrating with Activity Browser?

Answer: the Premise exercises focus on generating databases, inspecting changes, and running LCAs

39. Should there be a small case study that spans Brightway -> Premise -> Activity Browser?

Answer: Yes, we will follow a notebook to generate a few databases, and check them out in the brightway project.

40. Are there credentials, API keys, or local files needed for Premise that should not be committed to the repository?

Answer: Indeed. Premise requires an encryption key, which is key='tUePmX_S5B8ieZkkM7WUU2CnO8SmShwmAeWK9x2rTFo=‘. We will include this key in the environment YAML file as an environment variable, so that participants can easily set it up without needing to copy-paste it from the instructions. We will also include instructions in the README about how to obtain Premise credentials and set up the key.

## 8. Edges Module - 0.5 Day

41. Should Edges be a compact conceptual introduction plus one runnable example, or should it keep part of the current Day 2 regionalised LCIA sequence?

Answer: Currently, we have the Edges tutorials spanning over two days. We should somehow condense the Edges material to fit it in 0.5 day, while still providing a runnable example that illustrates the key concepts of exchange-based characterization and spatially differentiated LCIA. We can focus on the most relevant and impactful topics within Edges, and streamline the content to ensure it fits within the allocated time while still delivering a meaningful learning experience for participants.

42. Which current Edges topics should stay?

Possible topics:

- exchange-based characterization concept
- `edges` JSON method format
- spatial matching and fallback logic
- AWARE / biodiversity examples
- regionalized hydrogen pathways
- uncertainty in regionalized LCIA

Answer: exchange-based characterization concept, AWARE / biodiversity examples, and the inventory flow assessment tutorials.

43. Should Edges be linked to the same database/case study as Brightway/Premise, or be a standalone example?

Answer: this should not change. the notebooks are good as they are. They work with the BAFU database, we cna leave it that way.

44. Should the current Day 3 parameterized CF material be kept, moved to optional material, or removed?

Answer: It should be moved as optional notebooks that they can explore later on on their own.

## 9. Trails / Dynamic LCA Module - 0.5 Day Optional

45. What exactly should "Trails" refer to here: a specific package/workflow, or a broader dynamic LCA concept module?

Answer: It's a Python package that does dynamic LCA, and it is developed by the same team as Edges. It is a bit more experimental than Edges, but it is interesting to show it as an optional module if the group is fast.

46. Do you have existing Trails material or code to import into this repository?

Answer: Yes, we have some notebooks that we can adapt for this course. They are not as polished as the other modules, but they can be used as a starting point for the optional Trails module. Two are here: /Users/romain/Github/trails/examples Actually, teh first one does not require teh Premise data package.

47. Should Trails be an optional final notebook, a slide/demo handout, or a reserve exercise if the group is fast?

Answer: It should be an optional tutorial notebook that we can explore if we have enough time at the end of the course. We can prepare it in advance, but we will only cover it if we have enough time, as it is a bit more experimental and less mature than the other modules.

48. Should dynamic LCA connect to Premise scenarios, Edges parameterized CFs, or a separate example?

Answer: Indeed, Trails consumes a data package generated by Premise. So, we will have to generate that data package (which is not a regular Brightway database).

## 10. Current Content To Keep, Move, Or Drop

49. Should old Barcelona-specific regionalized LCIA/GeoPolRisk notebooks be removed from the active schedule, kept in an `optional/` folder, or archived elsewhere?

Answer: No, they should be kept in the active schedule, as they are good examples of how to do regionalized LCIA with the BAFU database. We can keep them as they are, as they are relevant for understanding how to do regionalized LCIA with Brightway and Edges.

50. Should the current hydrogen pathway case study stay in the new course?

Answer: Yes, it is a good example of how to do regionalized LCIA with the BAFU database, and it is relevant for understanding how to do regionalized LCIA with Brightway and Edges. We can keep it as it is, as it is a good example of how to do regionalized LCIA with Brightway and Edges.

51. Should the current inventory flow assessment / GeoPolRisk material stay?

Answer: Yes, it is a good example of how to do inventory flow assessment with Brightway and Edges, and it is relevant for understanding how to do inventory flow assessment with Brightway and Edges. We can keep it as it is, as it is a good example of how to do inventory flow assessment with Brightway and Edges.

52. Should the current home assignment be adapted or removed?

Answer: Should be removed.

53. Should the current reading list be adapted, shortened, or expanded?

Answer: Cna be kept.

54. Should the schedule remain notebook-by-notebook, or become a broader module agenda?

Answer: We can keep the schedule notebook-by-notebook, as it is easier for participants to follow and understand what they will be doing each day. We can also include a broader module agenda at the beginning of each day, to give participants an overview of the topics that will be covered and how they fit together. This way, we can provide both a high-level overview and a detailed breakdown of the course content. The exception being teh Activity Browser module, as it is a GUI.

## 11. Practical Deliverables

55. What files should be updated first?

Possible first pass:

- `README.MD`
- `INSTRUCTIONS.MD`
- `SCHEDULE.MD`
- day-level `README.MD` files
- environment YAML files
- notebook titles and project names

Answer: all of those listed above.

56. Do you want a new folder structure such as:

```text
tutorials/
  00_SETUP/
  DAY 1 - Brightway/
  DAY 2 - Brightway and Activity Browser part I/
  DAY 3 - Premise/
  DAY 4 - Activity Browser, Edges, Trails/
  OPTIONAL/
```

Answer: DAY 3 - Premise/Activity Browser part II/ and DAY 4 - Edges and Trails/ would be better, as the Activity Browser is used both on Day 2 and Day 3.

57. Should generated outputs stay out of the repository by default?

Answer:

58. Should notebooks include answer cells/templates, or should solutions be hidden/separate?

Answer: notebooks should include answer cells/templates. In general, let's keep the current notebooks style.

59. Should we prepare a participant-facing certificate/attendance note or just mention the 28 hours in the README?

Answer: no,let's completely remove that part.

60. Are there institutional branding requirements for Mines Paris - PSL or the lab?

Answer: No

## 12. Priority And Constraints

61. What is the most important learning outcome for participants after four days?

Answer: The most important learning outcome for participants after four days is to have a solid understanding of how to use Brightway, Premise, and Edges for LCA modeling and analysis. They should be able to import and work with LCA databases, generate prospective LCA databases using Premise, perform regionalized LCIA with Edges, and use the Activity Browser for advanced analysis and visualization. Additionally, they should have a good grasp of the underlying concepts and methodologies related to LCA, IAM scenarios, and exchange-based characterization.

62. What should be avoided because it is too advanced, too fragile, or not relevant for this audience?

Answer:

63. What should absolutely be preserved from the Barcelona course?

Answer:

64. What deadline should I work toward for a first adapted draft?

Answer:

65. Any other constraints or preferences?

Answer:

