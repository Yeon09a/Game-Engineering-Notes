# 𝐔𝐑𝐏-𝐛𝐚𝐬𝐞𝐝 𝐆𝐫𝐚𝐩𝐡𝐢𝐜𝐬 𝐚𝐧𝐝 𝐑𝐞𝐧𝐝𝐞𝐫𝐢𝐧𝐠 𝐎𝐩𝐭𝐢𝐦𝐢𝐳𝐚𝐭𝐢𝐨𝐧
In 2024, I ran into a performance issue while working on an XR game project. 
The game had three stages, and everything seemed to be working as expected during development and testing.


However, during a game exhibition, one of the stages started freezing repeatedly, and I had no choice but to remove that stage from the game.


At that point, I didn't have enough knowledge and experience with optimization to fix the issue. Since then, 
I've set a goal to learn performance optimization and apply what I learn in later projects.


In a game project I'm currently participating, I've decided to study graphics and rendering optimization and apply it to the game. 
To start with, I studied Unity's Quality Settings and URP Asset options, trying to understand how each option affects performance effects and visual quality.


Based on what I've learned, I created four quality levels, and modified the options for each level as follows:
1. Quality Settings : key options related to Graphics quality, such as Rendering, Texture, Particle, LOD, Mesh, and Async Asset Upload.
2. URP Asset : Graphics quality options related to Rendering, Lighting, Shadows, and Post-processing.


After adjusting the settings, I recorded Frame Time, System Used Memory, CPU Memory, and GPU Memory to compare differences between quality levels.


The tests were conducted in the Unity Editor environment using Unity Performance Testing Extension. 
I implemented a test script with Test Runner and Performance Testing API to run the tests on the same scene with identical conditions and player input, while only varying the quality level. 
The scene chosen for testing was the game play scene with the highest mesh and texture usage, and each test ran for 120 frames.


As a result of these tests, I was able to observe that the higher quality levels tended to increase Frame Time and CPU Render Thread Wait for GPU Time.
In addition, System Used Memory, Total Memory, CPU Memory, and GPU Memory also increased. On the other hand, CPU Main Thread Frame Time and CPU Render Thread Frame Time showed relatively small changes across the quality levels.


Through this test, I observed clear performance differences across the quality levels, confirming that each level behaved differenctly in practice.


The purpose of these tests was not to analyse the performance of each individual option, but to confirm that the settings for each quality level resulted in actual performance differences and that each level was distinct as intended.


At the moment, the project is not yet complete, so it doesn't have all the graphic assets we need. As a result, the differences between quality levels in this test are relatively small.
Once the game is more complete, I expect the performance differences between quality levels to be clearer.


After creating a prototype, I'm going to run not only the same graphic-related tests but also tests for code optimization, in a build environment.
