[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/O47Qftl8)
# IDG1293-2024-oblig2

This document contains the description for the second compulsory assignment of the course IDG1293.

# Goal

* Prove knowledge and understanding of SVGs, SVGs animations, CSS drawing, and CSS animations.
* Implement a poster design using HTML and CSS, preserving aspect ratio and ensuring responsiveness.
* Use SVGs and CSS drawing to animate parts of the poster for enhanced visual appeal.
* Encourage creativity and innovation in web design.
* Practice SASS.
* Practice your oral presentational skills.

# Introduction

**Scenario**

Digital sustainability is becoming increasingly important in today's world. NTNU has created a series of posters promoting digital sustainability, available in PDF format [here](https://www.ntnu.no/design/digital-barekraft/illustrasjoner). These posters are visually appealing for children and contain various elements that can be animated to create engaging web experiences.

# Context

In this "oblig" you will be presented with a brief description of the problem you have to solve. Have in mind the [Goal section](#Goal) when you design and implement your assignment. 

This is a group task, and you are required to build everything from the ground up. Although, you may utilize snippets of code from tutorials or official documentation, you must clearly acknowledge the sources in the comments of your code. Plagiarism or cheating will be deemed to have taken place if the submitted code shows substantial similarities to other students' assignments or projects found online. In such cases, the matter will be reported to the NTNU appeals committee for further examination. If you have any doubts regarding the use of materials for your project, please reach out to the instructor for clarification. 

It is imperative to deliver the assignment within the set deadline (never after).

## Task

1. **Select one of the posters and extract elements**:
    - Download the PDF posters from the provided link.
    - Use software like Adobe Illustrator to extract elements from the chosen poster.
    - Ensure that the extracted elements preserve the aspect ratio and are suitable for web implementation.
    - Optimise or rewrite the elements when needed.

2. **Implement poster design**:
    - Choose one of the posters extracted by the group.
    - Implement the poster design using HTML and CSS.
    - Ensure responsiveness and preserve the aspect ratio of the poster.

3. **Animate poster elements**:
    - Identify the primary illustrations suitable for animation, specifically selecting those that can demonstrate a good knowledge in various types of animations, including CSS animations, SMIL path animations, SMIL animate, and SMIL transform. Optionally, consider including GSAP animations.
    - Ensure that animated elements are incorporated into all sections of the posters to provide a comprehensive showcase of animation techniques.
    - Utilize SVGs and CSS drawing techniques to animate parts of the poster.
    - Enhance the visual appeal of the poster by adding animations that bring elements to life.
    - Aim for smooth transitions and engaging visual effects.

4. **Interactions (Optional)**:
    - While interactions with elements are allowed, focus on creating animations that enhance the poster's visual impact even without user interactions.
    - Experiment with hover effects, click interactions, etc., if time allows and if they contribute positively to the overall design.

5. **Documentation**:
    - Edit `documents/report.md` to explain your process and list all the elements you have animated, the type of animation you have used for each type and the reason why you used that type.

# Folder Structure

- `README.md`: This document describing the assignment.
- `index.html`: Main HTML file containing the implementation of the poster design.
- `assets/`: Folder containing extracted elements from the chosen poster (if needed).
- `assets/styles/styles.scss`: SCSS file containing styles for the poster design and animations.
- `misc/github-pages.pdf`: pdf file with instructions to deploy project in GitHub pages.
- `documents/report.md`: Document outlining the steps the group took during implementation.

# Delivery

This assignment must be delivered in two different places: GitHub classroom and Blackboard. The project must also be deployed in GitHub pages. Finally, the groups will brielfly present the poster orally and on campus (see datails on BB). 

* To deliver the assignment in GitHub Classroom, you only need to make sure all your changes and commits are pushed to your Git repository.
    * A Pull request is created automatically when the repository is cloned. Feedback will be included there if needed. Do not remove or close that Pull Request.
    * Only the changes in the "main" branch will be considered the final version. Do not close the other branches since we will look how you have collaborated using Git.

* It is imperative that you work exclusively with this Git repository to ensure that all modifications are trackable and your code is backed up on a regular basis. Hence, you should commit your progress directly to this repository each time you make advancements.

* Before delivering the assignment in Blackboard, make sure your project has all the files it needs. Delete any file, folder or info that is not needed (e.g.: `.git/` folder). Zip the project and upload the file to Blackboard. 
