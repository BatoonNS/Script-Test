using System;

namespace ProgrammingLAB3
{
    class Program
    {
        const Int32 MONTHSPERYEAR = 12;  
        static void Main(string[] args)
        {
            bool backTop = true;


            while (backTop)
            {
                Console.WriteLine("-------------------------");
                Console.WriteLine("Where would you like to go?");
                Console.WriteLine("1. Rainfall Statistics");
                Console.WriteLine("2. Charge Account Validation");
                Console.WriteLine("3. Quit the Menu");
                Console.WriteLine("-------------------------");
                String TempChoice;
                int MenuChoice;
                TempChoice = Console.ReadLine();
                MenuChoice = Convert.ToInt32(TempChoice);

                int menu = MenuChoice;
                switch (menu)
                {
                    case 1:
                        Console.WriteLine("1. Rainfall statistics");
                        RainfallStatistic();
                        break;
                    case 2:
                        Console.WriteLine("1. Charge Account Validation");
                        AccValidation();
                        break;
                    case 3:
                        Console.WriteLine("3. Quit the menu");
                        Console.WriteLine("Press enter to confirm exit");
                        Console.ReadLine();
                        Environment.Exit(0);
                        break;

                }
                
            }
        }
        static void RainfallStatistic()
        {         
            rainfall();
           
            static void rainfall()
            {
                Double[] Rainfall;
                Double totalrain, avg, Hrain, Lrain;
                Rainfall = new double[MONTHSPERYEAR];
                getuserinput(ref Rainfall);
                totalrain = caltotalrainfall(Rainfall);
                Console.WriteLine("The total rain for the year is " + totalrain);
                avg = averagerain(totalrain);
                Console.WriteLine("The average rainfall for this year is " + avg);
                Hrain = Highrain(Rainfall);
                int _Number = Convert.ToInt32(Hrain);
                String name = "";
                switch (_Number)
                {

                    case 0:
                        name = "January";
                        break;
                    case 1:
                        name = "Febuary";
                        break;
                    case 2:
                        name = "March";
                        break;
                    case 3:
                        name = "April";
                        break;
                    case 4:
                        name = "May";
                        break;
                    case 5:
                        name = "June";
                        break;
                    case 6:
                        name = "July";
                        break;
                    case 7:
                        name = "Augest";
                        break;
                    case 8:
                        name = "September";
                        break;
                    case 9:
                        name = "October";
                        break;
                    case 10:
                        name = "November";
                        break;
                    case 11:
                        name = "December";
                        break;
                    
                }
                Console.WriteLine("Highest rainfall month was " + name + " with " + Rainfall[Convert.ToInt32(Hrain)] + " units of rain");
                Lrain = Lowrain(Rainfall);
                int _Number2 = Convert.ToInt32(Lrain);
                String name2 = "";
                switch (_Number2)
                {

                    case 0:
                        name2 = "January";
                        break;
                    case 1:
                        name2 = "Febuary";
                        break;
                    case 2:
                        name2 = "March";
                        break;
                    case 3:
                        name2 = "April";
                        break;
                    case 4:
                        name2 = "May";
                        break;
                    case 5:
                        name2 = "June";
                        break;
                    case 6:
                        name2 = "July";
                        break;
                    case 7:
                        name2 = "Augest";
                        break;
                    case 8:
                        name2 = "September";
                        break;
                    case 9:
                        name2 = "October";
                        break;
                    case 10:
                        name2 = "November";
                        break;
                    case 11:
                        name2 = "December";
                        break;
                }
                Console.WriteLine("Lowest rainfall month was " + name2 + " with " + Rainfall[Convert.ToInt32(Lrain)] + " units of rain");

            }
            static void getuserinput(ref Double[] dumarray)
            {

                Console.WriteLine("Please enter the rain fall for each consecutive month, starting with January and ending in December, press enter after each input.");
                for (int i = 0; i < MONTHSPERYEAR; i++)
                {
                    Boolean realnum;
                    double b;
                    do
                    {
                        realnum = double.TryParse(Console.ReadLine(), out b);
                        if (realnum == true)
                        {
                            if (b < 0)
                            {
                                Console.WriteLine("You entered a negative number, try again");
                                realnum = false;
                            }
                        }
                        else
                        {
                            Console.WriteLine("Please try your number again");
                        }
                    }
                    while (realnum == false);
                    dumarray[i] = Convert.ToDouble(b);
                }

                return;
            }
            static Double caltotalrainfall(Double[] dumarray)
            {
                Double total = 0;

                for (int i = 0; i < MONTHSPERYEAR; i++)
                {
                    total = total + dumarray[i];
                }

                return total;
            }
            static double averagerain(double totalrain)
            {
                double avgrain;
                avgrain = totalrain / MONTHSPERYEAR;

                return avgrain;
            }


            static double Highrain(Double[] dumarray)
            {

                int Highest;
                Highest = 0;
                for (int i = 0; i < MONTHSPERYEAR; i++)
                {
                    if (dumarray[Highest] > dumarray[i])
                    {
                        
                    }
                    else
                    {
                        Highest = i;
                    }
                    
                }
                return Highest;
            }
            static double Lowrain(Double[] dumarray)
            {
                int Lowest;
                Lowest = 0;
                for (int i = 0; i < MONTHSPERYEAR; i++)
                {
                    if (dumarray[Lowest] < dumarray[i])
                    {
                        
                    }
                    else
                    {
                        Lowest = i;
                    }
                    
                }
                return Lowest;
            }
            Console.WriteLine("-----------------------------------");
            Console.WriteLine("Press enter to return to Main Menu");
            Console.WriteLine("-----------------------------------");
            Console.ReadLine();
            return;
        }
        static void AccValidation()
        {
            Int32[] Creditcheck = new Int32[18];
            Creditcheck[0] = 5658845;
            Creditcheck[1] = 4520125;
            Creditcheck[2] = 7895122;
            Creditcheck[3] = 8777541;
            Creditcheck[4] = 8451277;
            Creditcheck[5] = 1302850;
            Creditcheck[6] = 8080152;
            Creditcheck[7] = 4562555;
            Creditcheck[8] = 5552012;
            Creditcheck[9] = 5050552;
            Creditcheck[10] = 7825877;
            Creditcheck[11] = 1250255;
            Creditcheck[12] = 1005231;
            Creditcheck[13] = 6545231;
            Creditcheck[14] = 3852085;
            Creditcheck[15] = 7576651;
            Creditcheck[16] = 7881200;
            Creditcheck[17] = 4581002;

            Console.WriteLine("Please enter charge account number");
            bool foundit;
            int Chargeinput;
            Chargeinput = Convert.ToInt32(Console.ReadLine());

            foundit = Chargecheck(Creditcheck, Chargeinput);
            if (foundit)
            {
                Console.WriteLine("The Charge account is vaild. *SUCCESS*.");
            }
            else
            {
                Console.WriteLine("The Charge account was invaild, *Try Again*.");
            }
            static bool Chargecheck(int[] Creditcheck, int Chargeinput)
            {
                Boolean found = false;
                for(int i = 0; i<18; i++)
                {
                    if(Creditcheck[i] == Chargeinput)
                    {
                        found = true;
                        break;
                    }
                }
                return found;
            }
            Console.WriteLine("-----------------------------------");
            Console.WriteLine("Press enter to return to main menu");
            Console.WriteLine("-----------------------------------");
            Console.ReadLine();
        }


    }
}
