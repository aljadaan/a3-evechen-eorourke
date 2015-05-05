a3-evechen-eorourke
===============

## Team Members

1. Yvonne Chen evechen@uw.edu
2. Nell O'Rourke eorourke@cs.washington.edu

## Data Visualization: Assignment 3

## The DatasetFor this assignment, we chose to analyze data from our 10-week trial of the Enlearn Platform.  Enlearn is a non-profit company that Zoran founded to develop tablet-based adaptive educational software for use in elementary school classrooms.  The goal of the trial was to learn about the impact of using a tablet-based adaptive math curriculum in the classroom.  Eleven classes in four Seattle-area schools participated in the trial, with a total of 272 students.  Of these classes, seven used the tablet-based software and four served as a control and used traditional paper workbooks.  All eleven classes were exposed to the same material, but in the tablet-based classes, problems were delivered through the Enlearn software, and the sequence of practice problems adapted based on the performance of each individual student.The complexity and size of the data set does not lend itself to easy analysis, so we decided to create an interactive visualization that would help us explore the correlations between student behavior and learning gains.  In Assignment 2, Nell found that there are no clear correlations between student learning gains and the number of exercise problems completed, the percentage of assessment problems correct, or the number of teacher assists.  This was a surprising result, because we would expect these factors to have an impact on student learning.  We hypothesized that the design of the paper pre- and post-tests could be influencing the results, so we wanted to develop a visualization that would help us interact with the individual test items and find any interesting patterns.We chose to look at six different behavioral factors in this analysis, an expansion on the three factors that Nell examined in Assignment 2.  Our goal was to determine whether these factors correlate with learning gains, and whether there are any interesting patterns in these correlations based on condition and test type.  We give an overview of each of the factors explored in our visualization below:

- Number of Exercise Problems Completed: Students worked through exercise problems during class, either in their notebooks or on the tablets. We counted the number of these exercise problems each student completed, but did not grade the problems, since there were so many.- Number of Assessment (AP) Problems Completed: The curriculum included a set of more serious “AP” problems that were completed at certain checkpoints during the 10-week trial. We counted the number of the assessment problems that students were able to complete.- Percentage of Assessment (AP) Problems Correct: In addition to counting the number of assessment problems completed, we also graded these problems, so we calculated the percentage of completed problems that each student got correct.- Percentage of Observations On Task: During 10 observation days spread across the 10-week trial, we observed students and recorded their activity.  Specifically, at the moment of observation, we recorded whether the student was “on-task”, “off-task”, or “idle”. We calculated the percent of total observations during which each student was “on-task”. - Percentage of Observations Off Task: We calculated the percent of total observations during which each student was “off-task”. - Percentage of Observations Idle or ?: We calculated the percent of total observations during which each student was “idle”.  Sometimes, researchers were unsure how to classify student behavior, in which case the behavior was recorded as “?”. We combined the “idle” and “?” observations to calculate the percentage of time that students were neither on-task nor off-task.- Learning Gain: We gave students paper pre- and post-tests before two units during the 10-week trial. To calculate overall learning gains, we aggregated the pre- and post-test scores, and computed the difference between the post-test and pre-test to find each student’s overall learning gain. Negative scores indicate that a student performed worse on the post-tests than on the pre-tests.- Test Type: Students took pre-tests before each unit and post-tests after each unit. There were two versions of each test, an A version and a B version.  We gave half of the students the A version as their pre-test, and the other half the B version.  The students that had the A version as their pre-test received the B version as their post-test.  We were interested in exploring whether these tests were well balanced or not; if one test was more difficult than the other, this could impact our observed results.

##Final DesignOur interactive visualization provides an environment for exploring the data from the Enlearn Fall Trial.  The visualization includes one central data view, which shows six scatterplots and a stacked bar chart.  The scatterplots display the relationship between student learning gains and six different behavioral factors such as exercise problems solved and percentage of time spent on-task. The bar chart shows student performance on individual items in an assessment test.Buttons to the right of the screen allow the user to select from four different tests. When a new button is clicked, the bar chart updates to display the data for the associated test, and the dots in the scatterplot are re-colored.  The scatterplots’ y-axis shows student learning gains for the current unit.  Learning gains will differ between Unit 2 and Unit 4, so if the user selects a new unit, the y-axis will change to reflect the appropriate learning gains.We also allow the user to select which variable to examine, either grouping students by the test type they took (A vs B), or the experimental condition they belonged to (Tablet vs Paper).

## Running Instructions
Access our visualization at http://cse512-15s.github.io/a3-evechen-eorourke/  or download this repository and run `python -m SimpleHTTPServer 8000` and access this from http://localhost:8000/.

## Story Board

[Click here to view our storyboard](storyboard.pdf?raw=true).

### Changes between Storyboard and the Final Implementation

Our original plan involved graphing by condition and generating bars by test type, but we realized that this combination was quite limited. Therefore, we added a set of buttons that changes the grouping of students to either a grouping by test type or by experimental condition. The two groupings have separate color to prevent visual confusion when switching between grouping types.Initially, we planned to display two rows of six graphs, comparing students in the Paper condition to those in the Tablet condition. However, it was hard to display six graphs at once on the screen, so we plotted one graph for each factor, regardless of condition or type. This reduced the number of graphs to six, which we then displayed in two rows of three. We did consider that this decision might cause occlusion, so we reduced scatterplot dot size and increase color contrast.To interact with bars, users can click the bar itself, or the selection areas between, above and below the bars. During the development process, we realized that some bars may be small or non existent (such as some questions which no students answered correctly in a pre-test). To fix this, we increased the interactive footprint of each bar with some padding. The bar outline is highlighted on hover and the footprint turns light gray.

## Development Process

First, we met to brainstorm ideas for our visualization and storyboard our design.  After the storyboarding phase, Yvonne created an initial static mockup of our visualization design using D3 and JavaScript while Nell wrote scripts to format the Enlearn data and produce CSV files.  After the initial phase, we met to iterate on our design and plan out the interaction development.  Yvonne created the buttons for selecting the Unit and Test, and also wrote the code that handles hovering over bars using larger hit areas to make small bars more easily selectable.  Nell implemented code that handles clicking on bars and added the “Select All” and “Deselect All” buttons.  Nell also wrote the functionality to switch between the “Test Type” and “Condition” variables.  For the final write-up, Yvonne created the storyboard images and wrote a first draft of the write-up, and Nell filled in details about the data set and variables of interest. 

We spent around 25-30 hours developing our application, with coding taking up the majority of the time.
