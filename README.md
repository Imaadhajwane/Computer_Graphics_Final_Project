# Computer_Graphics_Final_Project

<h2>Overview</h2>
<p>This Java-based Car Game project involves a simple yet engaging car game where the player navigates a car on a road, avoiding obstacles, collecting points, and trying to achieve the highest score. The game is designed with basic 2D graphics and is an excellent example of how to implement a graphical user interface (GUI) and handle user inputs in Java.</p>

<h2>1. Classes and Their Responsibilities</h2>

<h3>1.1. CarGame Class</h3>
<ul>
    <li><strong>Inheritance and Interfaces:</strong>
        <ul>
            <li><strong>Extends:</strong> JFrame</li>
            <li><strong>Implements:</strong> KeyListener, ActionListener</li>
        </ul>
    </li>
    <li><strong>Purpose:</strong> This is the main class responsible for building the game's graphical interface, handling user inputs, managing game logic, and rendering all game elements on the screen.</li>
</ul>

<h2>2. Methods and Their Functions</h2>

<h3>2.1. Constructor: <code>CarGame(String title)</code></h3>
<ul>
    <li><strong>Purpose:</strong> Initializes the game window with specified properties such as size, visibility, layout, and event listeners.</li>
    <li><strong>Key Operations:</strong>
        <ul>
            <li>Sets the window size and position.</li>
            <li>Makes the window visible and non-resizable.</li>
            <li>Adds key listeners for user input.</li>
            <li>Sets default close operation.</li>
        </ul>
    </li>
</ul>

<h3>2.2. <code>paint(Graphics g)</code> Method</h3>
<ul>
    <li><strong>Purpose:</strong> Overrides the paint method of JFrame to render all game graphics, including the background, road, trees, player car, opponent cars, score, and game over screen.</li>
    <li><strong>Key Operations:</strong>
        <ul>
            <li>Draws the grass and road.</li>
            <li>Animates road lines to simulate movement.</li>
            <li>Loads and draws tree images, updating their positions to create a scrolling effect.</li>
            <li>Loads and draws the player's car and opponent cars, updating their positions.</li>
            <li>Detects collisions between the player's car and opponent cars.</li>
            <li>Updates and displays the score and speed.</li>
            <li>Handles game over state and displays the game over screen with a restart prompt.</li>
            <li>Implements a delay to control game speed.</li>
        </ul>
    </li>
</ul>

<h3>2.3. <code>main(String[] args)</code> Method</h3>
<ul>
    <li><strong>Purpose:</strong> Entry point of the application. Creates an instance of the CarGame class to start the game.</li>
</ul>

<h3>2.4. <code>keyPressed(KeyEvent e)</code> Method</h3>
<ul>
    <li><strong>Purpose:</strong> Handles key press events to move the player's car left or right and to restart the game when it's over.</li>
    <li><strong>Key Operations:</strong>
        <ul>
            <li>Moves the car left when the left arrow key is pressed, ensuring it doesn't go out of bounds.</li>
            <li>Moves the car right when the right arrow key is pressed, ensuring it doesn't go out of bounds.</li>
            <li>Restarts the game when the Enter key is pressed after a game over.</li>
        </ul>
    </li>
</ul>

<h3>2.5. <code>keyReleased(KeyEvent e)</code> Method</h3>
<ul>
    <li><strong>Purpose:</strong> Currently not implemented but required by the KeyListener interface.</li>
</ul>

<h3>2.6. <code>keyTyped(KeyEvent e)</code> Method</h3>
<ul>
    <li><strong>Purpose:</strong> Handles key typed events to move the player's car left or right using the 'a' and 'd' keys.</li>
    <li><strong>Key Operations:</strong>
        <ul>
            <li>Moves the car left when the 'a' key is pressed.</li>
            <li>Moves the car right when the 'd' key is pressed.</li>
            <li>Triggers a repaint to update the game's visuals.</li>
        </ul>
    </li>
</ul>

<h3>2.7. <code>actionPerformed(ActionEvent e)</code> Method</h3>
<ul>
    <li><strong>Purpose:</strong> Currently not implemented but required by the ActionListener interface.</li>
</ul>

<h2>3. Game Algorithm</h2>
<p>Below is a step-by-step algorithm that outlines the flow and logic of the CarGame:</p>

<h3>3.1. Initialization</h3>
<ul>
    <li><strong>Setup Game Window:</strong>
        <ul>
            <li>Create a JFrame with specified size (700x700 pixels) and position.</li>
            <li>Make the window visible and non-resizable.</li>
            <li>Set layout to null for absolute positioning.</li>
            <li>Add key listeners to handle user inputs.</li>
            <li>Initialize game variables such as car positions, opponent car positions, tree positions, score, speed, and delay.</li>
        </ul>
    </li>
    <li><strong>Load Images:</strong>
        <ul>
            <li>Load images for the player's car and opponent cars.</li>
            <li>Load tree images for environmental decoration.</li>
        </ul>
    </li>
</ul>

<h3>3.2. Game Loop (paint Method)</h3>
<ul>
    <li><strong>Render Background:</strong>
        <ul>
            <li>Draw grass and road using colored rectangles.</li>
            <li>Alternate road line positions to simulate road movement.</li>
        </ul>
    </li>
    <li><strong>Animate Trees:</strong>
        <ul>
            <li>Draw trees on both sides of the road.</li>
            <li>Increment tree Y-positions to move them downward.</li>
            <li>Reset tree positions to the top once they move off-screen.</li>
        </ul>
    </li>
    <li><strong>Render Player's Car:</strong>
        <ul>
            <li>Draw the player's car at its current X and Y positions.</li>
            <li>Update the Y-position to create a subtle forward movement effect.</li>
        </ul>
    </li>
    <li><strong>Render Opponent Cars:</strong>
        <ul>
            <li>Draw opponent cars at their current positions.</li>
            <li>Increment their Y-positions to move them downward.</li>
            <li>Reset opponent car positions once they move off-screen and randomize their new positions.</li>
        </ul>
    </li>
    <li><strong>Handle Opponent Car Collisions:</strong> Check for collisions between the player's car and each opponent car. If a collision is detected, set gameover to true.</li>
    <li><strong>Update Score and Speed:</strong>
        <ul>
            <li>Increment the score based on game progression.</li>
            <li>Increase the speed of the game to make it more challenging.</li>
            <li>Adjust the delay to control the game's frame rate and difficulty.</li>
        </ul>
    </li>
    <li><strong>Handle Game Over:</strong> If gameover is true, display a game over screen with a prompt to restart. Stop updating game elements until the player chooses to restart.</li>
    <li><strong>Repaint:</strong> Continuously call repaint() to refresh the game screen and continue the game loop.</li>
</ul>

<h3>3.3. User Input Handling</h3>
<ul>
    <li><strong>Key Pressed:</strong>
        <ul>
            <li><strong>Left Arrow Key:</strong> Move the player's car left, ensuring it doesn't go beyond the left boundary.</li>
            <li><strong>Right Arrow Key:</strong> Move the player's car right, ensuring it doesn't go beyond the right boundary.</li>
            <li><strong>Enter Key:</strong> If the game is over, reset all game variables to restart the game.</li>
        </ul>
    </li>
    <li><strong>Key Typed:</strong>
        <ul>
            <li>'a' Key: Move the player's car left.</li>
            <li>'d' Key: Move the player's car right.</li>
            <li>Trigger a repaint to update the car's new position.</li>
        </ul>
    </li>
</ul>

<h3>3.4. Collision Detection</h3>
<p>Continuously check if any opponent car overlaps with the player's car based on their X and Y positions. If an overlap is detected, initiate the game over sequence.</p>

<h3>3.5. Game Restart</h3>
<p>Upon pressing the Enter key after a game over:</p>
<ul>
    <li>Reset all game variables to their initial states.</li>
    <li>Clear any game over flags.</li>
    <li>Restart the game loop.</li>
</ul>

<h2>4. Recommendations for Improvement</h2>
<p>While your game is functional, here are some suggestions to enhance its structure and performance:</p>

<ul>
    <li><strong>Separate Concerns:</strong>
        <ul>
            <li><strong>Create Additional Classes:</strong> Consider creating separate classes for game elements like PlayerCar, OpponentCar, Tree, etc. This will make your code more modular and easier to manage.</li>
        </ul>
    </li>
    <li><strong>Optimize Image Loading:</strong>
        <ul>
            <li><strong>Load Images Once:</strong> Currently, images are loaded inside the paint method, which is called repeatedly. Move image loading to the constructor or an initialization method to avoid redundant loading and improve performance.</li>
        </ul>
    </li>
    <li><strong>Use Double Buffering:</strong>
        <ul>
            <li><strong>Prevent Flickering:</strong> Implement double buffering to smooth out animations and prevent flickering during repainting.</li>
        </ul>
    </li>
    <li><strong>Improve Collision Detection:</strong>
        <ul>
            <li><strong>Use Bounding Boxes:</strong> Instead of simple position checks, use bounding boxes or more precise collision detection methods to enhance accuracy.</li>
        </ul>
    </li>
    <li><strong>Enhance Game Loop:</strong>
        <ul>
            <li><strong>Use javax.swing.Timer:</strong> Utilize a Timer to manage the game loop instead of relying on repaint() calls and Thread.sleep(). This provides better control over the game's timing and responsiveness.</li>
        </ul>
    </li>
    <li><strong>Handle Resizing and Scaling:</strong>
        <ul>
            <li><strong>Responsive Design:</strong> Although the window is set to be non-resizable, designing your game to handle different window sizes can make it more flexible.</li>
        </ul>
    </li>
    <li><strong>Add Sound Effects and Music:</strong>
        <ul>
            <li><strong>Enhance User Experience:</strong> Incorporate sound effects for actions like moving, collisions, and game over to make the game more engaging.</li>
        </ul>
    </li>
    <li><strong>Implement a Scoring System:</strong>
        <ul>
            <li><strong>Display High Scores:</strong> Track and display high scores to motivate players to improve.</li>
        </ul>
    </li>
</ul>


<h2>5. Folders</h2>
<p>This Repository contains one folder named "images". It contains 4 car images that are used as driver's car and rest of the car are used as obstracles. It also has a tree images that are used as design element in the GUI</p>

<h2>6. Code File</h2>
<p>The code for the game is present in "CarJava.java" file</p>

<h2>7. How to Clone and Run the Project</h2>

<h3>Step 1: Clone the Repository</h3>
<p>To clone the GitHub repository, use the following command in your terminal or command prompt.</p>
<pre>
<code>git clone https://github.com/Imaadhajwane/Computer_Graphics_Final_Project.git</code>
</pre>

<h3>Step 2: Navigate to the Project Directory</h3>
<p>After cloning, navigate into the directory of the project:</p>
<pre>
<code>cd Computer_Graphics_Final_Project</code>
</pre>

<h3>Step 3: Compile the Java File</h3>
<p>Assuming you have Java installed, you can compile the <code>CarJava.java</code> file using the <code>javac</code> command:</p>
<pre>
<code>javac CarJava.java</code>
</pre>

<h3>Step 4: Run the Java Program</h3>
<p>Once the compilation is successful, run the program using the <code>java</code> command:</p>
<pre>
<code>java CarJava</code>
</pre>


