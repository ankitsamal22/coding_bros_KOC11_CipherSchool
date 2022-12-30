# coding_bros_KOC11_CipherSchool
# Function for Date,Month and Year is valid or not !!!
def check_valid_date(date):
    day = int(date[0] + date[1])
    month = int(date[2] + date[3])
    year = int(date[4] + date[5] + date[6] + date[7])

    if month == 1 or month == 3 or month == 5 or month == 7 or month == 8 or month == 10 or month == 12:
        max_days = 31
    elif month == 4 or month == 6 or month == 9 or month == 11:
        max_days = 30
    elif year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
        max_days = 29
    else:
        max_days = 28

    if month < 1 or month > 12:
        print("Please check the entered value !!")
    elif day < 1 or day > max_days:
        print("Please check the entered value !!")
    elif year < 0 or year > 9999:
        print("Invalid Year !!")
    # else:
    #     print("Valid Input")


# Function for checking leap year !!!
def check_leap_yr(year):
    if year % 4 == 0:
        if year % 100 == 0:
            if year % 400 == 0:
                print(year, end=" ")
        else:
            print(year, end=" ")
    return True


# 1. input first date as string in the format dd/mm/yyyy
date1 = str(input("Enter first Date in dd/mm/yyyy: "))
# 2. replacing forward slash from string
first_date = date1.replace("/", "")
# 3. checking that the inputted date is valid or not
check_valid_date(first_date)
# 4. taking out last four characters from string i.e, yyyy
st_yr = str(first_date[4] + first_date[5] + first_date[6] + first_date[7])
# 5. converting firs string into integer
int_st_yr = int(st_yr)

# 6. Input end date as string in the format dd/mm/yyyy
date2 = str(input("Enter Second Date in dd/mm/yyyy: "))
# 7. replacing forward slash from string
sec_date = date2.replace("/", "")
# 8. checking that the inputted date is valid or not
check_valid_date(sec_date)
# 9. taking out last four characters from string i.e, yyyy
end_yr = str(sec_date[4] + sec_date[5] + sec_date[6] + sec_date[7])
# 10. converting firs string into integer
int_end_yr = int(end_yr)


print(f"Non-Leap year between {date1} and {date2} are :-")
# 12. create for loop to print non leap years.
for i in range(int_st_yr, int_end_yr+1):
    if i % 4 != 0:
        print(i, end=" ")


print(f"\nLeap year between {date1} and {date2} are :-")
# 11. create while loop for output by calling leap yr function.
while int_st_yr <= int_end_yr:
    check_leap_yr(int_st_yr)
    int_st_yr += 1

print("\n")
