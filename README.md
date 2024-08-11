<p align="center">
  <img src="./ReadMeAssets/RoboDashHeader.gif" alt="RoboDash Logo" width="200">
</p>
<h1 align="center">RoboDash</h1>

<p align="center">
  <strong>RoboDash</strong> is an engaging endless runner game developed using Unreal Engine's Blueprint system. It showcases dynamic path creation, collision handling, event-driven programming, and game optimization, delivering a smooth, interactive, and visually appealing gaming experience.
</p>

<h2>Project Overview</h2>
<p>
  The goal of RoboDash was to design and develop an endless runner game using Unreal Engine's Blueprint system. This project demonstrates proficiency in dynamic path creation, collision handling, event-driven programming, and game optimization. The game was intended as a rapid prototype to showcase a working knowledge of Unreal Engine.
</p>

<h2>Tools & Technologies</h2>
<ul>
  <li><strong>Engine:</strong> Unreal Engine</li>
  <li><strong>Visual Scripting:</strong> Unreal Blueprints</li>
</ul>

<h2>Project Summary</h2>
<p>
  RoboDash is an endless runner game where players must avoid obstacles and collect donuts to win. The game was developed as a proof of concept to demonstrate my skills in using Unreal Engine. It features seamless tile spawning, dynamic obstacle interactions, and comprehensive character controls.
</p>

<h2>Scenarios</h2>

<!-- SCENARIO1 -->
<h3 id="floor-spawning"> :small_orange_diamond: Scenario 1: Floor Spawning Logic</h3>
<p>
  In this scenario, the game manages seamless tile spawning and destruction triggered by player collisions, ensuring continuous and efficient gameplay. This blueprint handles spawning new tiles and destroying old ones to maintain seamless gameplay and efficient memory usage.
</p>
<ul>
  <li><strong>Tile Spawning:</strong> The <code>OnComponentBeginOverlap</code> event for the EndTrigger component triggers when the player collides with it. If the colliding actor is of the type <code>BP_NT3000_C</code>, the game mode is retrieved, and a new floor tile is spawned at the end of the current sequence, ensuring the endless nature of the game.</li>
  <li><strong>Tile Destruction:</strong> To manage memory, the <code>OnComponentBeginOverlap</code> event for the Box component detects collisions with obstacles. After a 2-second delay, the Destroy Actor function is called, programmatically removing the specified tile or obstacle from the game.</li>
</ul>

<!-- SCENARIO2 -->
<h3 id="obstacles"> :small_orange_diamond: Scenario 2: Obstacles</h3>
<p>
  This scenario focuses on defining collision behavior for obstacles using Unreal Engine's Blueprint system. The <code>OnComponentHit</code> event triggers collision detection, and the <code>On Collision With Obstacle</code> function handles interactions such as damaging the player or triggering animations.
</p>
<ul>
  <li><strong>Collision Detection:</strong> The <code>OnComponentHit</code> event for the StaticMesh component is triggered when an obstacle collides with another object. If the collision is with <code>BP_NT3000_C</code>, the <code>On Collision With Obstacle</code> function is called to manage the interaction.</li>
  <li><strong>Collision Handling:</strong> The <code>On Collision With Obstacle</code> function includes responses such as damaging the player, triggering animations, or other game-specific behaviors.</li>
</ul>

<!-- SCENARIO3 -->
<h3 id="character-controls"> :small_orange_diamond: Scenario 3: Character Controls and Behavior</h3>
<p>
  In this scenario, the character's controls and behaviors are developed, including continuous forward movement, corner turning, left/right movement, and jumping, along with collision handling for game-over scenarios and a pause menu system.
</p>
<ul>
  <li><strong>Player Movement:</strong> The character moves forward continuously, turns at corners, moves left/right, and jumps based on input.</li>
  <li><strong>Collision with Obstacles:</strong> When the character collides with an obstacle, the <code>OnCollisionWithObstacle</code> event triggers, setting the character's state to dead, disabling input, and displaying the loss screen.</li>
  <li><strong>Pause Menu:</strong> The pause menu system is toggled with the <code>Input Action Menu</code>, enabling UI mode for interaction.</li>
</ul>

<!-- SCENARIO4 -->
<h3 id="obstacle-spawning"> :small_orange_diamond: Scenario 4: Obstacle and Collectible Spawning</h3>
<p>
  This scenario covers the implementation of a system for dynamic obstacle and collectible spawning, ensuring varied and engaging gameplay by strategically placing challenges and rewards throughout the game environment.
</p>
<ul>
  <li><strong>Donut Spawning:</strong> The <code>Donut Spawner for Pickup</code> function randomly places donut pickups within a defined area on a floor tile, using the <code>Random Point in Bounding Box</code> to determine spawn locations.</li>
  <li><strong>Obstacle Spawning:</strong> The <code>Obstacle and Donut Alternately Spawn Logic</code> function alternates between spawning obstacles and donuts, using a random integer to decide what to spawn, ensuring varied gameplay.</li>
</ul>

<!-- SCENARIO5 -->
<h3 id="gameplay-enhancement"> :small_orange_diamond: Scenario 5: Gameplay Enhancement</h3>
<p>
  In this scenario, the game’s challenge and variety are enhanced by implementing logic to randomize the tiles spawned while ensuring no paradox paths are created.
</p>
<ul>
  <li><strong>Corner and Ramp Spawning:</strong> The blueprint logic decides whether to spawn a floor tile, corner tile, or ramp, using a randomizer to ensure varied gameplay.</li>
  <li><strong>Endless Path Illusion:</strong> The <code>SpawnActor</code> node spawns new tiles at the end of the sequence, creating the illusion of an endless path. The system tracks consecutive straight tiles to prevent paradox paths.</li>
</ul>

<h2>Contributing</h2>
<p>Fork the repository and submit a pull request with your improvements or bug fixes.</p>

<h2>License</h2>
<p>This project is licensed under the <a href="LICENSE">MIT License</a>.</p>
