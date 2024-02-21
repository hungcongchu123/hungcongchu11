Console.WriteLine("Water bill calculation program:");

void CalculateWaterBill()
{
    string customer = "";

    // Adding exception handling for invalid customer names
    while (string.IsNullOrWhiteSpace(customer))
    {
        Console.WriteLine("Enter customer's full name:");
        customer = Convert.ToString(Console.ReadLine());
        if (string.IsNullOrWhiteSpace(customer))
        {
            Console.WriteLine("Invalid customer name. Please enter again.");
        }
    }

    Console.WriteLine("Please choose customer type:");
    Console.WriteLine("Enter 1 if you are a household customer");
    Console.WriteLine("Enter 2 if you are an administrative agency:");
    Console.WriteLine("Enter 3 if you are a manufacturing unit");
    Console.WriteLine("Enter 4 if you are a business service customer");
    int typeCustomer = Convert.ToInt32(Console.ReadLine());

    if (typeCustomer == 1)
    {
        // Household customer
        // Request the number of family members
        Console.WriteLine("ENTER THE NUMBER OF FAMILY MEMBERS:");
        int familyMembers = Convert.ToInt32(Console.ReadLine());
        if (familyMembers >= 1)
        {
            Console.WriteLine("Enter the water meter reading of the previous month:");
            int waterPreviousMonth = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Enter the water meter reading of this month:"); 
            int waterCurrentMonth = Convert.ToInt32(Console.ReadLine());
            if (waterPreviousMonth <= waterCurrentMonth)
            {
                int totalWater = waterCurrentMonth - waterPreviousMonth;
                double waterPerPerson = totalWater / familyMembers;
                if (waterPerPerson > 0 && totalWater <= 10)
                {
                    double bill = (totalWater * 5.973) * 1.1;
                    Console.WriteLine("{0:N}VND total water bill:", bill);
                }
                else if (waterPerPerson > 10 && waterPerPerson <= 20)
                {
                    double bill = (totalWater * 7.052) * 1.1;
                    Console.WriteLine("{0:N}VND total water bill:", bill);
                }
                else if (waterPerPerson > 20 && waterPerPerson <= 30)
                {
                    double bill = (totalWater * 8.699) * 1.1;
                    Console.WriteLine("{0:N}VND total water bill:", bill);
                }
                else
                {
                    double bill = (totalWater * 15.929) * 1.1;
                    Console.WriteLine("{0:N}VND total water bill:", bill);
                }
            }
            else
            {
                Console.Write("Water consumption of the previous month must be less than or equal to this month ");
            }
        }
        else
        {
            Console.WriteLine("You are not a household customer:");
        }
    }
    else if (typeCustomer == 2)
    {
        // Administrative agency customer/-strong/-heart:>:o:-((:-hConsole.WriteLine("Enter the water meter reading of the previous month:");
        int waterPreviousMonth = Convert.ToInt32(Console.ReadLine());
        Console.WriteLine("Please enter the current month's water meter reading:");
        int waterCurrentMonth = Convert.ToInt32(Console.ReadLine());
        if (waterPreviousMonth <= waterCurrentMonth)
        {
            double bill = (waterCurrentMonth - waterPreviousMonth) * 9955 * 1.1;
            Console.WriteLine("{0:N}VND water bill for administrative public service agency", bill);
        }
        else
        {
            Console.WriteLine("Water bill of the previous month cannot be greater than this month");
        }
    }
    else if (typeCustomer == 3)
    {
        // Manufacturing unit customer
        Console.WriteLine("Enter the water meter reading of the previous month:");
        int waterPreviousMonth = Convert.ToInt32(Console.ReadLine());
        Console.WriteLine("Please enter the current month's water meter reading:");
        int waterCurrentMonth = Convert.ToInt32(Console.ReadLine());
        if (waterPreviousMonth <= waterCurrentMonth)
        {
            double bill = (waterCurrentMonth - waterPreviousMonth) * 11.615 * 1.1;
            Console.WriteLine("{0:N}VND water bill for manufacturing unit", bill);
        }
        else
        {
            Console.WriteLine("Water bill of the previous month cannot be greater than this month");
        }
    }
    else if (typeCustomer == 4)
    {
        // Business service customer
        Console.WriteLine("Enter the water meter reading of the previous month:");
        int waterPreviousMonth = Convert.ToInt32(Console.ReadLine());
        Console.WriteLine("Please enter the current month's water meter reading:");
        int waterCurrentMonth = Convert.ToInt32(Console.ReadLine());
        if (waterPreviousMonth <= waterCurrentMonth)
        {
            double bill = (waterCurrentMonth - waterPreviousMonth) * 22.068 * 1.1;
            Console.WriteLine("{0:N}VND water bill for business service", bill);
        }
        else
        {
            Console.WriteLine("Water bill of the previous month cannot be greater than this month");
        }
    }
    else
    {
        Console.WriteLine("Error! Please enter the customer type again:");
    }
}

// Run the program
CalculateWaterBill(); 
