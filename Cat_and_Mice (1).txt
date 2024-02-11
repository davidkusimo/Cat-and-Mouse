/*
Cat_and_Mice.java




David Kusimo 350743092
ICS4U Mr Palladini
This application is used as a class for a game of Cat and Mice.
*/




import java.util.Scanner;
import java.util.Random;


public class Main {


        // DATA DECLARATION
        // INSTANCE VARIABLES
        private final int MIN = 0;
        private final int MAX = 10;
        private int facingDirection;
        private int position_x;
        private int position_y;
        private String animal;




        //METHOD DECLARATION
        // CONSTRUCTOR METHOD: SETS UP THE ANIMAL TO HAVE AN ANIMAL NAME, AN INITIAL POSITION OF 0, AN INITIAL FACING DIRECTION OF 1 (RIGHT) AND TO BE TRUE (ALIVE).
        public Main(String animal) {
                this.position_x = 0;
                this.position_y = 0;
                this.facingDirection = 1;
                this.animal = animal;
        }




        // THIS METHOD SIMULATES THE CAT MOVING FORWARDS OR BACKWARDS BY 1 UNIT BETWEEN 0 AND 10 SPACES FROM THE ORIGIN IN THE Y AND X AXIS.
        // THE DIRECTION OF THE CAT DEPENDS ON THE VALUE OF THE facingDirection VARIABLE.
        // IF THE facingDirection = 1, CAT FACES RIGHT. IF THE facingDirection = 2, CAT FACES LEFT.
        // IF THE facingDirection = 3, CAT FACES UP. IF THE facingDirection = 4, CAT FACES DOWN.
        // IF THE CAT IS FACING LEFT IT MOVE BACKWARDS AND IF THE CAT IS FACING RIGHT IT MOVE FORWARDS.
        // IF THE CAT IS FACING UP IT MOVES UPWARDS AND IF THE CAT IS FACING DOWN IT MOVES DOWNWARDS.
        public void move(){


                if (facingDirection == 1 && position_x < MAX) {
                        position_x++;
                }
                else if (facingDirection == 2 && position_x > MIN) {
                        position_x--;
                }
                else if (facingDirection == 3 && position_y < MAX) {
                        position_y++;
                }
                else if (facingDirection == 4 && position_y > MIN) {
                        position_y--;
                }
        }


        // THIS METHOD SIMULATES THE MOUSE MOVING FORWARDS OR BACKWARDS BY 1 UNIT BETWEEN 0 AND 10 SPACES FROM THE ORIGIN.
        // THE DIRECTION OF THE MOUSE DEPENDS ON THE VALUE OF THE facingDirection VARIABLE.
        // IF THE facingDirection = 1, MOUSE FACES RIGHT. IF THE facingDirection = 2, MOUSE FACES LEFT.
        // IF THE facingDirection = 3, MOUSE FACES UP. IF THE facingDirection = 4, MOUSE FACES DOWN.
        // IF THE MOUSE IS FACING LEFT IT MOVE BACKWARDS AND IF THE MOUSE IS FACING RIGHT IT MOVE FORWARDS.
        // IF THE MOUSE IS FACING UP IT MOVES UPWARDS AND IF THE MOUSE IS FACING DOWN IT MOVES DOWNWARDS.
        public void moveMouse(int newPositionx, int newPositiony){


                // THE POSITION OF THE MOUSE IS SET TO IT'S STARTING POSITION FROM THE DRIVER.
                position_x = newPositionx;
                position_y = newPositiony;


                if (facingDirection == 1 && position_x < MAX) {
                        position_x++;
                }
                else if (facingDirection == 2 && position_x > MIN) {
                        position_x--;
                }
                else if (facingDirection == 3 && position_y < MAX) {
                        position_y++;
                }
                else if (facingDirection == 4 && position_y > MIN) {
                        position_y--;
                }
        }






        // THIS METHOD SETS THE FACING DIRECTION VARIABLE A VALUE.
        // A NEW DIRECTION INTEGER VALUE IS INPUT.
        public void setFacingDirection(int newDirection) {
                facingDirection = newDirection;
        }


        // THIS METHOD RETURNS THE FACING DIRECTION VALUE.
        // IT RETURNS THE FACING DIRECTION AS AN INTEGER.
        public int getFacingDirection() {
                return facingDirection;
        }


        // GETTER METHOD: RETURNS THE POSITION ON THE X-AXIS OF THE ANIMAL.
        public int getPosition_x() {
                return position_x;
        }


        // GETTER METHOD: RETURNS THE POSITION ON THE Y-AXIS OF THE ANIMAL.
        public int getPosition_y() {
                return position_y;
        }


        // toString() METHOD: RETURNS THE STATUS OF THE ANIMAL.
        // THE STATUS OF THE ANIMAL INCLUDES THE NAME OF THE ANIMAL (EITHER CAT OR MOUSE), X-AXIS POSITION, Y-AXIS POSITION AND FACING DIRECTION.
        public String toString() {
                return animal + " X:" + position_x + " Y:" + position_y + " " + facingDirection;
        }




        public static void main(String[] args) {
                Scanner input = new Scanner(System.in);
                Random ran = new Random();




                // INSTANTIATING FOUR MAIN OBJECTS. ONE CAT OBJECT AND THREE MOUSE OBJECTS.
                // THE NAME OF THE ANIMAL IS INPUT TO THE CONSTRUCTOR METHOD.
                Main cat = new Main("cat");
                Main mouse1 = new Main("mouse");
                Main mouse2 = new Main("mouse");
                Main mouse3 = new Main("mouse");




                // VARIABLES ARE MADE FOR THE AMOUNT OF STEPS THE CAT WILL MOVE AND THE FACING DIRECTION CHOICE.
                // TWO VARIABLES ARE ALSO MADE FOR THE X-AXIS AND Y-AXIS LOCATION OF THE CAT.
                int moveChoice;
                int choice;
                int new_Locationx = 0;
                int new_Locationy = 0;


                // BOOLEAN STATUS VARIABLES ARE MADE FOR EACH OF THE THREE MICE
                boolean mouse1_status = true;
                boolean mouse2_status = true;
                boolean mouse3_status = true;


                // AN INTEGER FACING DIRECTION OF THE MOUSE IS MADE TO HOLD THE VALE OF THE FACING DIRECTION.
                // TWO VARIABLES ARE ALSO MADE FOR THE X-AXIS AND Y-AXIS LOCATION OF EACH MOUSE.
                // THE LOCATION VARIABLES FOR EACH MOUSE ARE SET TO A CUSTOM POSITION TO PLACE THE MOUSE AT A CERTAIN LOCATION.
                int mouseDirection;
                int mouse1_new_Locationx = 5;
                int mouse1_new_Locationy = 5;
                int mouse2_new_Locationx = 3;
                int mouse2_new_Locationy = 7;
                int mouse3_new_Locationx = 8;
                int mouse3_new_Locationy = 2;




                // THE CUSTOM LOCATION VARIABLES ARE PLACED IN THE MOVE MOUSE METHOD TO CORRECTLY PLACE THE MICE IN THEIR DESIRED LOCATIONS.
                // THE FACING DIRECTION FOR EACH MOUSE IS SET TO ZERO SO THAT THE MOUSE DOES NOT MOVE AS THE INITIAL LOCATION OF THE MOUSE IS BEING SET.
                mouse1.setFacingDirection(0);
                mouse1.moveMouse(mouse1_new_Locationx, mouse1_new_Locationy);
                mouse2.setFacingDirection(0);
                mouse2.moveMouse(mouse2_new_Locationx, mouse2_new_Locationy);
                mouse3.setFacingDirection(0);
                mouse3.moveMouse(mouse3_new_Locationx, mouse3_new_Locationy);
                
                


                // A DO WHILE LOOP RUNS WHILE EACH MOUSE IS ALIVE AND STOPS WHEN THEY ARE ALL DEAD.
                do {


                        // THE STATUS OF EACH ANIMAL OBJECT IS PRINTED, WHICH INCLUDES THE X-AXIS AND Y-AXIS LOCATIONS WITH THE FACING DIRECTION VALUE FOR EACH.
                        System.out.println("\n" + cat);
                        System.out.println(" ");
                        if (mouse1_status) {
                                System.out.println(mouse1);
                        }
                        if (mouse2_status) {
                                System.out.println(mouse2);
                        }
                        if (mouse3_status) {
                                System.out.println(mouse3);
                        }
                        


                        // THE CHOICE OF THE CAT MOVING 1 OR 2 SPACES IS PRINTED OUT HERE.
                        System.out.println("\n" + "Do you want the cat to move 1 or 2 spaces (enter the number you want)?");
                        moveChoice = input.nextInt();


                        //THE 4 OPTIONS FOR THE USER ARE DISPLAYED FOR THE FACING DIRECTION OF THE CAT.
                        System.out.println("\n" + "Enter your choice for the direction the cat faces:");
                        System.out.println("1. Face right");
                        System.out.println("2. Face left");
                        System.out.println("3. Face upwards");
                        System.out.println("4. Face downwards");
                        choice = input.nextInt();
                        cat.setFacingDirection(choice);




                        // WHEN THE USER ENTERS TWO FOR THE NUMBER OF TIMES THE CAT MOVES, DEPENDING ON THE FACING DIRECTION, THE CAT WILL MOVE 2 SPACES.
                        // IF THE USER'S PREDICTED MOVEMENT IS OUT OF THE 10x10 GRID, THE CAT DOESN'T MOVE AND AN ERROR MESSAGE IS PRINTED.
                        if (moveChoice == 2) {


                                if (cat.getFacingDirection() == 1 && cat.getPosition_x() >= 9) {
                                        System.out.println("Sorry you can't move there.");
                                }
                                else if (cat.getFacingDirection() == 1 && cat.getPosition_x() < 9) {
                                        cat.move();
                                        cat.move();
                                        new_Locationx = cat.getPosition_x();
                                        System.out.println("The cat is at (" + new_Locationx + "," + new_Locationy + ")");
                                }
                                else if (cat.getFacingDirection() == 2 && cat.getPosition_x() <= 1) {
                                        System.out.println("Sorry you can't move there.");
                                }
                                else if (cat.getFacingDirection() == 2 && cat.getPosition_x() > 1) {
                                        cat.move();
                                        cat.move();
                                        new_Locationx = cat.getPosition_x();
                                        System.out.println("The cat is at (" + new_Locationx + "," + new_Locationy + ")");
                                }
                                else if (cat.getFacingDirection() == 3 && cat.getPosition_y() >= 9) {
                                        System.out.println("Sorry you can't move there.");
                                }
                                else if (cat.getFacingDirection() == 3 && cat.getPosition_x() < 9) {
                                        cat.move();
                                        cat.move();
                                        new_Locationy = cat.getPosition_y();
                                        System.out.println("The cat is at (" + new_Locationx + "," + new_Locationy + ")");
                                }
                                else if (cat.getFacingDirection() == 4 && cat.getPosition_y() <= 1) {
                                        System.out.println("Sorry you can't move there.");
                                }
                                else if (cat.getFacingDirection() == 4 && cat.getPosition_x() > 1) {
                                        cat.move();
                                        cat.move();
                                        new_Locationy = cat.getPosition_y();
                                        System.out.println("The cat is at (" + new_Locationx + "," + new_Locationy + ")");
                                }




                        }




                        // WHEN THE USER ENTERS ONE FOR THE NUMBER OF TIMES THE CAT MOVES, DEPENDING ON THE FACING DIRECTION, THE CAT WILL MOVE 1 SPACE.
                        // IF THE USER'S PREDICTED MOVEMENT IS OUT OF THE 10x10 GRID, THE CAT DOESN'T MOVE AND AN ERROR MESSAGE IS PRINTED.
                        else if (moveChoice == 1) {


                                if (cat.getFacingDirection() == 1 && cat.getPosition_x() < 10) {
                                        cat.move();
                                        new_Locationx = cat.getPosition_x();
                                        System.out.println("The cat is at (" + new_Locationx + "," + new_Locationy + ")");
                                }
                                else if (cat.getFacingDirection() == 1 && cat.getPosition_x() >= 10) {
                                        System.out.println("Sorry you can't move there.");
                                }
                                else if (cat.getFacingDirection() == 2 && cat.getPosition_x() > 0) {
                                        cat.move();
                                        new_Locationx = cat.getPosition_x();
                                        System.out.println("The cat is at (" + new_Locationx + "," + new_Locationy + ")");
                                }
                                else if (cat.getFacingDirection() == 2 && cat.getPosition_x() <= 0) {
                                        System.out.println("Sorry you can't move there.");
                                }
                                else if (cat.getFacingDirection() == 3 && cat.getPosition_y() < 10) {
                                        cat.move();
                                        new_Locationx = cat.getPosition_y();
                                        System.out.println("The cat is at (" + new_Locationx + "," + new_Locationy + ")");
                                }
                                else if (cat.getFacingDirection() == 3 && cat.getPosition_y() >= 10) {
                                        System.out.println("Sorry you can't move there.");
                                }
                                else if (cat.getFacingDirection() == 4 && cat.getPosition_y() > 0) {
                                        cat.move();
                                        new_Locationx = cat.getPosition_y();
                                        System.out.println("The cat is at (" + new_Locationx + "," + new_Locationy + ")");
                                }
                                else if (cat.getFacingDirection() == 4 && cat.getPosition_y() <= 0) {
                                        System.out.println("Sorry you can't move there.");
                                }


                        }




                        // IF STATEMENTS FOR THE 1st MOUSE
                        // IF THE MOUSE IS NOT ON THE SAME BOX AS A MOUSE, THE IF STATEMENT WILL CONTINUE TO RUN AND THE MOUSE WIll CONTINUE TO MOVE.
                        // A RANDOM NUMBER IS GENERATED TO RANDOMLY CHOOSE A NUMBER BETWEEN 1-4 TO SET THE FACING DIRECTION OF THE 1st MOUSE.
                        // DEPENDING ON THE NUMBER GENERATED THE MOUSE WILL MOVE ONE SPACE IN THAT DIRECTION.


                        if (mouse1_new_Locationx != new_Locationx && mouse1_new_Locationy != new_Locationy && mouse1_status) {
                                mouseDirection = ran.nextInt(4) + 1;
                                mouse1.setFacingDirection(mouseDirection);




                                //THE LOCATION OF THE X-AXIS AND Y-AXIS OF THE 1st MOUSE IS INPUT TO THE MOVE MOUSE METHOD.
                                if (mouse1.getFacingDirection() == 1 && mouse1.getPosition_x() < 10) {
                                        mouse1.moveMouse(mouse1_new_Locationx, mouse1_new_Locationy);
                                        mouse1_new_Locationx = mouse1.getPosition_x();
                                }
                                else if (mouse1.getFacingDirection() == 2 && mouse1.getPosition_x() > 0) {
                                        mouse1.moveMouse(mouse1_new_Locationx, mouse1_new_Locationy);
                                        mouse1_new_Locationx = mouse1.getPosition_x();
                                        
                                }
                                else if (mouse1.getFacingDirection() == 3 && mouse1.getPosition_y() < 10) {
                                        mouse1.moveMouse(mouse1_new_Locationx, mouse1_new_Locationy);
                                        mouse1_new_Locationy = mouse1.getPosition_y();
                                }
                                else if (mouse1.getFacingDirection() == 4 && mouse1.getPosition_y() > 0) {
                                        mouse1.moveMouse(mouse1_new_Locationx, mouse1_new_Locationy);
                                        mouse1_new_Locationy = mouse1.getPosition_y();
                                }
                        }


                        // IF THE CAT LANDS ON THE SAME BOX AS A MOUSE, THE MOUSE WILL DIE AND THE STATUS OF THE MOUSE WILL BECOME FALSE.
                        // A MESSAGE OF THE MOUSE BEING CAUGHT IS PRINTED.
                        if (mouse1_new_Locationx == new_Locationx && mouse1_new_Locationy == new_Locationy && mouse1_status) {
                                mouse1_status = false;
                                System.out.println("1 mouse has been caught!");
                        }




                        // IF STATEMENTS FOR THE 2nd MOUSE
                        // IF THE MOUSE IS NOT ON THE SAME BOX AS A MOUSE, THE IF STATEMENT WILL CONTINUE TO RUN AND THE MOUSE WIll CONTINUE TO MOVE.
                        // A RANDOM NUMBER IS GENERATED TO RANDOMLY CHOOSE A NUMBER BETWEEN 1-4 TO SET THE FACING DIRECTION OF THE 2nd MOUSE.
                        // DEPENDING ON THE NUMBER GENERATED THE MOUSE WILL MOVE ONE SPACE IN THAT DIRECTION.
                        if (mouse2_new_Locationx != new_Locationx && mouse2_new_Locationy != new_Locationy && mouse2_status) {
                                mouseDirection = ran.nextInt(4) + 1;
                                mouse2.setFacingDirection(mouseDirection);


                                //THE LOCATION OF THE X-AXIS AND Y-AXIS OF THE 2nd MOUSE IS INPUT TO THE MOVE MOUSE METHOD.
                                if (mouse2.getFacingDirection() == 1 && mouse2.getPosition_x() < 10) {
                                        mouse2.moveMouse(mouse2_new_Locationx, mouse2_new_Locationy);
                                        mouse2_new_Locationx = mouse2.getPosition_x();
                                }
                                else if (mouse2.getFacingDirection() == 2 && mouse2.getPosition_x() > 0) {
                                        mouse2.moveMouse(mouse2_new_Locationx, mouse2_new_Locationy);
                                        mouse2_new_Locationx = mouse2.getPosition_x();
                                }
                                else if (mouse2.getFacingDirection() == 3 && mouse1.getPosition_y() < 10) {
                                        mouse2.moveMouse(mouse2_new_Locationx, mouse2_new_Locationy);
                                        mouse2_new_Locationy = mouse2.getPosition_y();
                                }
                                else if (mouse2.getFacingDirection() == 4 && mouse2.getPosition_y() > 0) {
                                        mouse2.moveMouse(mouse2_new_Locationx, mouse2_new_Locationy);
                                        mouse2_new_Locationy = mouse2.getPosition_y();
                                }
                        }


                        // IF THE CAT LANDS ON THE SAME BOX AS A MOUSE, THE MOUSE WILL DIE AND THE STATUS OF THE MOUSE WILL BECOME FALSE.
                        // A MESSAGE OF THE MOUSE BEING CAUGHT IS PRINTED.
                        if (mouse2_new_Locationx == new_Locationx && mouse2_new_Locationy == new_Locationy && mouse2_status) {
                                mouse2_status = false;
                                System.out.println("1 mouse has been caught!");
                        }




                        // IF STATEMENTS FOR THE 3rd MOUSE
                        // IF THE MOUSE IS NOT ON THE SAME BOX AS A MOUSE, THE IF STATEMENT WILL CONTINUE TO RUN AND THE MOUSE WIll CONTINUE TO MOVE.
                        // A RANDOM NUMBER IS GENERATED TO RANDOMLY CHOOSE A NUMBER BETWEEN 1-4 TO SET THE FACING DIRECTION OF THE 3rd MOUSE.
                        // DEPENDING ON THE NUMBER GENERATED THE MOUSE WILL MOVE ONE SPACE IN THAT DIRECTION.
                        if (mouse3_new_Locationx != new_Locationx && mouse3_new_Locationy != new_Locationy && mouse3_status) {
                                mouseDirection = ran.nextInt(4) + 1;
                                mouse3.setFacingDirection(mouseDirection);


                                //THE LOCATION OF THE X-AXIS AND Y-AXIS OF THE 3rd MOUSE IS INPUT TO THE MOVE MOUSE METHOD.
                                if (mouse3.getFacingDirection() == 1 && mouse3.getPosition_x() < 10) {
                                        mouse3.moveMouse(mouse3_new_Locationx, mouse3_new_Locationy);
                                        mouse3_new_Locationx = mouse3.getPosition_x();
                                }
                                else if (mouse3.getFacingDirection() == 2 && mouse3.getPosition_x() > 0) {
                                        mouse3.moveMouse(mouse3_new_Locationx, mouse3_new_Locationy);
                                        mouse3_new_Locationx = mouse3.getPosition_x();
                                }
                                else if (mouse3.getFacingDirection() == 3 && mouse1.getPosition_y() < 10) {
                                        mouse3.moveMouse(mouse3_new_Locationx, mouse3_new_Locationy);
                                        mouse3_new_Locationy = mouse3.getPosition_y();
                                }
                                else if (mouse3.getFacingDirection() == 4 && mouse3.getPosition_y() > 0) {
                                        mouse3.moveMouse(mouse3_new_Locationx, mouse3_new_Locationy);
                                        mouse3_new_Locationy = mouse3.getPosition_y();
                                }
                        }


                        // IF THE CAT LANDS ON THE SAME BOX AS A MOUSE, THE MOUSE WILL DIE AND THE STATUS OF THE MOUSE WILL BECOME FALSE.
                        // A MESSAGE OF THE MOUSE BEING CAUGHT IS PRINTED.
                        if (mouse3_new_Locationx == new_Locationx && mouse3_new_Locationy == new_Locationy && mouse3_status) {
                                mouse3_status = false;
                                System.out.println("1 mouse has been caught!");
                        }
                } while (mouse1_status || mouse2_status || mouse3_status);
                
                // FINAL STATEMENT IS OUTPUT AFTER THE GAME HAS ENDED.
                System.out.println("All the mice are dead! The cat wins once again.");
        }
}