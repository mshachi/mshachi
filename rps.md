class Program
    {

        public static int cpWins { get; set; }
        public static int charWins { get; set; }
       static void Run()
        {
                Console.Clear();
                String mainHR = "=====================================================================";
                String subHR = "---------------------------------------------------------------------";
                String errorInvalid = "\nPlease enter a valid input.";
                String checkuserInput = "\n\tYour input: ";
                String comChoice;
                String charChoice;
                String choiceVal;
                
                int charHealth = 100;
                int enemyHealth = 100;

                void gameOver()
                {
                    Console.Clear();
                    Console.WriteLine("\t\tThe player surrendered.");
                    Console.WriteLine("\t\tGame Over!");

                    do
                    {
                        Console.WriteLine(subHR);
                        Console.WriteLine("Do you wish to restart the game?");
                        Console.WriteLine("\nInput 'Y' to continue; input 'N' to exit. ");
                        String input = Console.ReadLine().ToUpper();

                        if (input == "Y")
                        {
                            Run();

                        }
                        else if (input == "N")
                        {
                            Environment.Exit(0);
                        }
                        else
                        {
                            Console.Clear();
                            Console.WriteLine("What do you mean by '{0}'? Please enter either 'Y' or 'N'", input);

                        }
                    } while (true);

                }

                void finalDec()
                {
                    if (charHealth <= 0)
                    {
                    cpWins++;
                    Console.WriteLine("\t\tThe Anonymous Wizard Wins!");
                    Console.WriteLine("\n Anonymous Wizard: {0}\t\tPlayer Wins: {1}", cpWins, charWins);


                    do
                    {
                            Console.WriteLine(subHR);
                            Console.WriteLine("Do you wish to continue?");
                            Console.WriteLine("\nInput 'Y' to continue; input 'N' to exit. ");
                            String input = Console.ReadLine().ToUpper();

                            if (input == "Y")
                            {
                                Run();

                            }
                            else if (input == "N")
                            {
                                Environment.Exit(0);
                            }
                            else
                            {
                                Console.Clear();
                                Console.WriteLine("What do you mean by '{0}'? Please enter either 'Y' or 'N'", input);
                            }
                        } while (true);


                    }
                    else if (enemyHealth <= 0)
                    {

                       
                        Console.WriteLine("\t\tThe Player Wins!");
                        Console.WriteLine("\n Anonymous Wizard: {0}\t\tPlayer Wins: {1}", cpWins, charWins);


                    do
                    {
                            Console.WriteLine(subHR);
                            Console.WriteLine("Do you wish to continue?");
                            Console.WriteLine("\nInput 'Y' to continue; input 'N' to exit. ");
                            String input = Console.ReadLine().ToUpper();

                            if (input == "Y")
                            {
                                Run();

                            }
                            else if (input == "N")
                            {
                                Environment.Exit(0);
                            }
                            else
                            {
                                Console.Clear();
                                Console.WriteLine("What do you mean by '{0}'? Please enter either 'Y' or 'N'", input);

                            }
                        } while (true);


                    }
                    else { }
                }

                void checkGame()
                {
                if (charChoice == "fire magic" && comChoice == "perennial magic")
                {
                    Console.WriteLine("\t\tFire defeats Perennial.\n");
                    Console.BackgroundColor = ConsoleColor.DarkBlue;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tOpponent has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    enemyHealth -= 20;
                    finalDec();
                }
                else if (charChoice == "water magic" && comChoice == "fire magic")
                {
                    Console.WriteLine("\t\tWater defeats Fire.\n");
                    Console.BackgroundColor = ConsoleColor.DarkBlue;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tOpponent has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    enemyHealth -= 20;
                    finalDec();
                }
                else if (charChoice == "perennial magic" && comChoice == "water magic")
                {
                    Console.WriteLine("\t\tPerennial defeats Water.\n");
                    Console.BackgroundColor = ConsoleColor.DarkBlue;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tOpponent has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    enemyHealth -= 20;
                    finalDec();
                }
                else if (comChoice == "perennial magic" && charChoice == "water magic")
                {
                    Console.WriteLine("\t\tPerennial defeats Water.\n");
                    Console.BackgroundColor = ConsoleColor.DarkRed;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tPlayer has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    charHealth -= 20;
                    finalDec();
                }
                else if (comChoice == "\t\tfire magic" && charChoice == "perennial magic")
                {
                    Console.WriteLine("\t\tFire defeats Perennial.\n");
                    Console.BackgroundColor = ConsoleColor.DarkRed;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tPlayer has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    charHealth -= 20;
                    finalDec();
                }
                else if (comChoice == "water magic" && charChoice == "fire magic")
                {
                    Console.WriteLine("\t\tWater defeats Fire.\n");
                    Console.BackgroundColor = ConsoleColor.DarkRed;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tPlayer has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    charHealth -= 20;
                    finalDec();
                }
                else if (charChoice == "unknown magic")
                {

                    Console.WriteLine("\t\tPlayer was unable to successfully summon magic!\n");
                    Console.BackgroundColor = ConsoleColor.DarkRed;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tPlayer has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    charHealth -= 25;
                    finalDec();
                }

                else
                {
                    Console.WriteLine("\t\tAn element defeats its own\n");

                    enemyHealth -= 10;
                    charHealth -= 10;
                    finalDec();
                }
            }

                do
                {
                    Console.WriteLine(mainHR);
                    Console.ForegroundColor = ConsoleColor.Black;
                    Console.BackgroundColor = ConsoleColor.Yellow;
                    Console.WriteLine("                        RPS Wizards                       ");
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.BackgroundColor = ConsoleColor.Black;
                Console.WriteLine("\nInput 'S' to start;   Input 'W' to view Guide;   Input 'D' to exit. ");
                    Console.Write(checkuserInput);

                    String mainmenuInput = Console.ReadLine().ToUpper();

                    Console.Clear();

                    if (mainmenuInput == "S")
                    {
                        do
                        {
                            Console.WriteLine(mainHR);
                            Console.Write("Input a name for your character: ");
                            String charName = Console.ReadLine();

                            bool name = charName.Any(char.IsDigit);

                            if (name == false)
                            {
                                if (charName.Any(char.IsDigit))
                                {

                                }

                                Console.Clear();
                                Console.WriteLine("\nIs '{0}' your character's name?", charName);
                                Console.WriteLine("'S' to proceed\t'D' to return to main menu\t Input any other key or string to rename");
                                Console.Write(checkuserInput);
                                String charnameInput = Console.ReadLine().ToUpper();

                                Console.Clear();

                                if (charnameInput == "S")
                                {

                                    string enemyName = "Anonymous Wizard";


                                    do
                                    {
                                    Console.WriteLine(subHR);
                                    Console.BackgroundColor = ConsoleColor.DarkRed;
                                    Console.ForegroundColor = ConsoleColor.White;
                                    Console.Write("\n'1' for fire magic");
                                    Console.BackgroundColor = ConsoleColor.Blue;
                                    Console.ForegroundColor = ConsoleColor.White;
                                    Console.Write("\t'2' for water magic");
                                    Console.BackgroundColor = ConsoleColor.Green;
                                    Console.ForegroundColor = ConsoleColor.White;
                                    Console.Write("\t'3' for plant magic");
                                    Console.BackgroundColor = ConsoleColor.White;
                                    Console.ForegroundColor = ConsoleColor.Black;
                                    Console.WriteLine("\t'4' to forfeit");
                                    Console.BackgroundColor = ConsoleColor.Black;
                                    Console.ForegroundColor = ConsoleColor.White;


                                    Console.Write("{0}'s Health: {1}%\t", charName, charHealth);
                                    Console.WriteLine("\t{0}'s Health: {1}%", enemyName, enemyHealth);

                                        var random = new Random();
                                        var list = new List<string> { "fire magic", "water magic", "perennial magic", 
                                            "water magic", "perennial magic", "fire magic" };
                                        int index = random.Next(list.Count);
                                        comChoice = list[index];



                                        Console.Write(checkuserInput);
                                        charChoice = Console.ReadLine();
                                        Console.BackgroundColor = ConsoleColor.Yellow;
                                        Console.ForegroundColor = ConsoleColor.Black;
                                        Console.WriteLine("\n\tIs {0} your final option?", charChoice);
                                        Console.BackgroundColor = ConsoleColor.Black;
                                        Console.ForegroundColor = ConsoleColor.White;
                                        Console.WriteLine("\n\t'Y' to proceed\t'Any key' to change magic");
                                        Console.Write("\n\tYour input: ");
                                        choiceVal = Console.ReadLine().ToUpper();
                                        if (choiceVal == "Y")
                                        {
                                            switch (charChoice)
                                            {
                                                case "1":
                                                    charChoice = "fire magic";
                                                    break;
                                                case "2":
                                                    charChoice = "water magic";
                                                    break;
                                                case "3":
                                                    charChoice = "perennial magic";
                                                    break;
                                                case "4":
                                                    gameOver();
                                                    break;

                                                default:
                                                    charChoice = "unknown magic";
                                                    break;

                                            }
                                            Console.Clear();
                                            Console.WriteLine("\n\t\tOpponent Chose: {0}\t", comChoice);
                                            Console.WriteLine("\n\t\tPlayer Chose: {0}\t\n", charChoice);
                                            checkGame();
                                        }
                                        else
                                        {
                                            Console.Clear();
                                            //back to choosing magic
                                        }



                                    } while ((charHealth > 0) || (enemyHealth > 0));
                                }
                                else if (charnameInput == "D")
                                {
                                    break;
                                    // goes back to main menu
                                }

                                else
                                {

                                }
                            }
                            else
                            {
                            Console.BackgroundColor = ConsoleColor.Red;
                            Console.ForegroundColor = ConsoleColor.White;
                            Console.WriteLine("Sorry, letters only!");
                            }
                        }
                        while (true);
                    }
                    else if (mainmenuInput == "D")
                    {
                        Console.WriteLine(mainHR);
                        break;
                    }
                    else if (mainmenuInput == "W")
                    {
                        Console.Clear();
                        Console.WriteLine(mainHR);
                        Console.ForegroundColor = ConsoleColor.Black;
                        Console.BackgroundColor = ConsoleColor.Yellow;
                        Console.WriteLine("                             RPS WIZARDS GUIDE                                     ");
                        Console.ForegroundColor = ConsoleColor.Yellow;
                        Console.BackgroundColor = ConsoleColor.Black;
                        Console.WriteLine("\nRules");
                        Console.ForegroundColor = ConsoleColor.White;
                        Console.BackgroundColor = ConsoleColor.Black;
                        Console.WriteLine("-Only letters are allowed for naming te player character.");
                        Console.WriteLine("\n-Forfeiting is considered a loss. ");
                        Console.WriteLine("\n-You");
                        Console.WriteLine("\n-There are 3 rounds so do your best to win twice or ace all rounds ");
                        Console.ForegroundColor = ConsoleColor.Yellow;
                        Console.BackgroundColor = ConsoleColor.Black;
                        Console.WriteLine("\nTips");
                        Console.ForegroundColor = ConsoleColor.White;
                        Console.BackgroundColor = ConsoleColor.Black;
                        Console.WriteLine("-If you forfeit it is considered a defeat ");
                        Console.WriteLine("\n-Pyro defeats Perennial");
                        Console.WriteLine("\n-Hydro defeats Pyro");
                        Console.WriteLine("\n-Perennial defeats Hydro ");
                        Console.ForegroundColor = ConsoleColor.Yellow;
                        Console.BackgroundColor = ConsoleColor.Black;
                        Console.WriteLine("\n\nPress any key to go back to main menu");
                        Console.ForegroundColor = ConsoleColor.White;
                        Console.BackgroundColor = ConsoleColor.Black;

                        Console.ReadLine();
                        Console.Clear();
                }
                    else
                    {
                        Console.WriteLine(errorInvalid);
                    }
                }
                while (true);
            } //same contents as main. just to rerun and restart the whole code as the method gets called

            static void Main(string[] args)
        {
           
            String mainHR = "=====================================================================";
            String subHR = "---------------------------------------------------------------------";
            String errorInvalid = "\nPlease enter a valid input.";
            String checkuserInput = "\n\tYour input: ";
            String comChoice;
            String charChoice;
            String choiceVal;
            String charName;
            
            int charHealth = 100;
            int enemyHealth = 100;

            void gameOver()
            {
                Console.Clear();
                Console.WriteLine("\t\tThe player surrendered.");
                Console.WriteLine("\t\tGame Over!");

                do
                {
                    Console.WriteLine(subHR);
                    Console.WriteLine("Do you wish to restart the game?");
                    Console.WriteLine("\nInput 'Y' to continue; input 'N' to exit. ");
                    String input = Console.ReadLine().ToUpper();

                    if (input == "Y")
                    {
                        Run();

                    }
                    else if (input == "N")
                    {
                        Environment.Exit(0);
                    }
                    else
                    {
                        Console.Clear();
                        Console.WriteLine("What do you mean by '{0}'? Please enter either 'Y' or 'N'", input);

                    }
                } while (true);

            }

            void finalDec() //method to determine the winner
            {
                if (charHealth <= 0)
                {
                    cpWins++;
                    Console.WriteLine("\t\tThe Anonymous Wizard Wins!");
                    Console.WriteLine("\n Anonymous Wizard: {0}\t\tPlayer Wins: {1}", cpWins, charWins);

                    do
                    {
                        Console.WriteLine(subHR);
                        Console.WriteLine("Do you wish to continue?");
                        Console.WriteLine("\nInput 'Y' to continue; input 'N' to exit. ");
                        String input = Console.ReadLine().ToUpper();

                        if (input == "Y")
                        {
                            Run();


                        }
                        else if (input == "N")
                        {
                            Environment.Exit(0);
                        }
                        else
                        {
                            Console.Clear();
                            Console.WriteLine("What do you mean by '{0}'? Please enter either 'Y' or 'N'", input);
                        }
                    } while (true);


                }
                else if (enemyHealth <= 0)
                {

                    charWins++;
                    Console.WriteLine("\t\tThe Player Wins!");
                    Console.WriteLine("\n Anonymous Wizard: {0}\t\tPlayer Wins: {1}", cpWins, charWins);
                    
                    
                    do
                    {
                        Console.WriteLine(subHR);
                        Console.WriteLine("Do you wish to continue?");
                        Console.WriteLine("\nInput 'Y' to continue; input 'N' to exit. ");
                        String input = Console.ReadLine().ToUpper();

                        if (input == "Y")
                        {
                            Run();

                        }
                        else if (input == "N")
                        {
                            Environment.Exit(0);
                        }
                        else
                        {
                            Console.Clear();
                            Console.WriteLine("What do you mean by '{0}'? Please enter either 'Y' or 'N'", input);
                            
                        }
                    } while (true);


                }
                else { }
            }

            void checkGame()
            {
                if (charChoice == "fire magic" && comChoice == "perennial magic")
                {
                    Console.WriteLine("\t\tFire defeats Perennial.\n");
                    Console.BackgroundColor = ConsoleColor.DarkBlue;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tOpponent has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    enemyHealth -= 20;
                    finalDec();
                }
                else if (charChoice == "water magic" && comChoice == "fire magic")
                {
                    Console.WriteLine("\t\tWater defeats Fire.\n");
                    Console.BackgroundColor = ConsoleColor.DarkBlue;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tOpponent has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    enemyHealth -= 20;
                    finalDec();
                }
                else if (charChoice == "perennial magic" && comChoice == "water magic")
                {
                    Console.WriteLine("\t\tPerennial defeats Water.\n");
                    Console.BackgroundColor = ConsoleColor.DarkBlue;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tOpponent has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    enemyHealth -= 20;
                    finalDec();
                }
                else if (comChoice == "perennial magic" && charChoice == "water magic")
                {
                    Console.WriteLine("\t\tPerennial defeats Water.\n");
                    Console.BackgroundColor = ConsoleColor.DarkRed;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tPlayer has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    charHealth -= 20;
                    finalDec();
                }
                else if (comChoice == "\t\tfire magic" && charChoice == "perennial magic")
                {
                    Console.WriteLine("\t\tFire defeats Perennial.\n");
                    Console.BackgroundColor = ConsoleColor.DarkRed;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tPlayer has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    charHealth -= 20;
                    finalDec();
                }
                else if (comChoice == "water magic" && charChoice == "fire magic")
                {
                    Console.WriteLine("\t\tWater defeats Fire.\n");
                    Console.BackgroundColor = ConsoleColor.DarkRed;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tPlayer has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    charHealth -= 20;
                    finalDec();
                }
                else if (charChoice == "unknown magic")
                {
                    
                    Console.WriteLine("\t\tPlayer was unable to successfully summon magic!\n");
                    Console.BackgroundColor = ConsoleColor.DarkRed;
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.WriteLine("\t\tPlayer has taken damage\n");
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.ForegroundColor = ConsoleColor.White;
                    charHealth -= 25;
                    finalDec();
                }

                else 
                {
                    Console.WriteLine("\t\tAn element defeats its own\n");

                    enemyHealth -= 10;
                    charHealth -= 10;
                    finalDec();
                }
            }

            do
            {
                Console.WriteLine(mainHR);
                Console.ForegroundColor = ConsoleColor.Black;
                Console.BackgroundColor = ConsoleColor.Yellow;
                Console.WriteLine("                      RPS Wizards                       ");
                Console.ForegroundColor = ConsoleColor.White;
                Console.BackgroundColor = ConsoleColor.Black;
                Console.WriteLine("\nInput 'S' to start;  Input 'W' to view Guide;   Input 'D' to exit. ");
                Console.Write(checkuserInput);

                String mainmenuInput = Console.ReadLine().ToUpper();

                Console.Clear();

                if (mainmenuInput == "S")
                {
                    do
                    {
                        Console.WriteLine(mainHR);
                        Console.Write("Input a name for your character: ");
                        charName = Console.ReadLine();

                        bool name = charName.Any(char.IsDigit);

                        if (name == false) { 
                            if (charName.Any(char.IsDigit)){
                            
                            }

                            Console.Clear();
                            Console.WriteLine("\nIs '{0}' your character's name?", charName);
                            Console.WriteLine("'S' to proceed\t'D' to return to main menu\t Input any other key or string to rename");
                            Console.Write(checkuserInput);
                            String charnameInput = Console.ReadLine().ToUpper();

                            Console.Clear();

                            if (charnameInput == "S")
                            {
                                
                                string enemyName = "Anonymous Wizard";
                            

                                do
                                {
                                    Console.WriteLine(subHR);
                                    Console.BackgroundColor = ConsoleColor.DarkRed;
                                    Console.ForegroundColor = ConsoleColor.White;
                                    Console.Write("\n'1' for fire magic");
                                    Console.BackgroundColor = ConsoleColor.Blue;
                                    Console.ForegroundColor = ConsoleColor.White;
                                    Console.Write("\t'2' for water magic");
                                    Console.BackgroundColor = ConsoleColor.Green;
                                    Console.ForegroundColor = ConsoleColor.White;
                                    Console.Write("\t'3' for plant magic");
                                    Console.BackgroundColor = ConsoleColor.White;
                                    Console.ForegroundColor = ConsoleColor.Black;
                                    Console.WriteLine("\t'4' to forfeit");
                                    Console.BackgroundColor = ConsoleColor.Black;
                                    Console.ForegroundColor = ConsoleColor.White;
                                    Console.Write("{0}'s Health: {1}%\t", charName, charHealth);
                                    Console.WriteLine("\t{0}'s Health: {1}%", enemyName, enemyHealth);

                                    var random = new Random();
                                    var list = new List<string> { "fire magic", "water magic", "perennial magic", "water magic", 
                                        "perennial magic", "fire magic" }; //repeated some of the choices to assure the randomness of the computer choice
                                    int index = random.Next(list.Count);                                                                                              
                                    comChoice = list[index];
                                    


                                    Console.Write(checkuserInput);
                                    charChoice = Console.ReadLine();
                                    Console.BackgroundColor = ConsoleColor.Yellow;
                                    Console.ForegroundColor = ConsoleColor.Black;
                                    Console.WriteLine("\n\tIs {0} your final option?", charChoice);
                                    Console.BackgroundColor = ConsoleColor.Black;
                                    Console.ForegroundColor = ConsoleColor.White;
                                    Console.WriteLine("\n\t'Y' to proceed\t'Any key' to change magic");
                                    Console.Write("\n\tYour input: ");
                                    choiceVal = Console.ReadLine().ToUpper();
                                    if (choiceVal == "Y")
                                    {
                                            switch (charChoice)
                                            {
                                                case "1":
                                                    charChoice = "fire magic";
                                                    break;
                                                case "2":
                                                    charChoice = "water magic";
                                                    break;
                                                case "3":
                                                    charChoice = "perennial magic";
                                                    break;
                                                case "4":
                                                    gameOver();
                                                    break;

                                                default:
                                                    charChoice = "unknown magic";
                                                    break;

                                            }
                                            Console.Clear();
                                            Console.WriteLine("\n\t\tOpponent Chose: {0}\t", comChoice);
                                            Console.WriteLine("\n\t\tPlayer Chose: {0}\t\n", charChoice);
                                            checkGame();
                                    } 
                                    else
                                    {
                                        Console.Clear();
                                        //back to choosing magic (user choice)
                                    }



                                } while ((charHealth > 0) || (enemyHealth > 0) );
                            }
                            else if (charnameInput == "D")
                            {
                                break;
                                // goes back to main menu
                            }
                       
                            else
                            {
                                //goes back to the naming part
                            }
                        }
                        else
                        {
                            Console.WriteLine("Sorry, letters only!");
                        }
                    }
                    while (true);
                }
                else if (mainmenuInput == "D")
                {
                    Console.WriteLine(mainHR);
                    break;
                }
                else if (mainmenuInput == "W")
                {
                    Console.Clear();
                    Console.WriteLine(mainHR);
                    Console.ForegroundColor = ConsoleColor.Black;
                    Console.BackgroundColor = ConsoleColor.Yellow;
                    Console.WriteLine("                             RPS WIZARDS GUIDE                                     ");
                    Console.ForegroundColor = ConsoleColor.Yellow;
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.WriteLine("\nRules");
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.WriteLine("-Only letters are allowed for naming te player character.");
                    Console.WriteLine("\n-Forfeiting is considered a loss. ");
                    Console.WriteLine("\n-You");
                    Console.WriteLine("\n-There are 3 rounds so do your best to win twice or ace all rounds ");
                    Console.ForegroundColor = ConsoleColor.Yellow;
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.WriteLine("\nTips");
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.WriteLine("-If you forfeit it is considered a defeat ");
                    Console.WriteLine("\n-Pyro defeats Perennial");
                    Console.WriteLine("\n-Hydro defeats Pyro");
                    Console.WriteLine("\n-Perennial defeats Hydro ");
                    Console.ForegroundColor = ConsoleColor.Yellow;
                    Console.BackgroundColor = ConsoleColor.Black;
                    Console.WriteLine("\n\nPress any key to go back to main menu");
                    Console.ForegroundColor = ConsoleColor.White;
                    Console.BackgroundColor = ConsoleColor.Black;

                    Console.ReadLine();
                    Console.Clear();
                }
                else
                {
                    Console.WriteLine(errorInvalid);
                }
            }
            while (true);
        }
    }
