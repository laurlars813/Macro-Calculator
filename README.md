#determine ideal calories
#multiply by set percentages
#Finally, divide your calorie amounts by its calorie-per-gram number.
#inputs weight and height
#basal metabolic rate female w * 4.35 h *4.7 sum them and * by 655
#sed = 1.2  lighlt active 1.375 m active 1.55 v active 1.725
# basal metabolo * life style = calories



def macros():
    gender = str(input("What is your gender?: Female or Male"))
    w = int(input("Hello, What is your weight in lbs?"))
    h = float(input("Thanks, what is your height in feet.inches?"))
    a = int(input("What is your age?"))
    if gender == "Female":
        BMR = ((w*4.35) + (h*4.7) - (a*4.7)) + 655
    else:
        BMR = ((w*6.24) + (h*12.7)) - (a*6.75) + 66.47

    al = str(input("What is your activity level?: Sedentary, Light Active, Active, or Highly Active?"))

    if al == "Sedentary":
        al = 1.2
    elif al == "Light Active":
        al = 1.375
    elif al == "Active":
        al = 1.55
    elif al == "Highly Active":
        al = 1.725
    else:
        print("Invalid Activity Level")

    calories = BMR * al
    print("Your Maintenance Calories are: " + str(calories))
    fats = (.25 * calories/9)
    carbs = (.50 * calories/4)
    protein = round(.25 * calories/4, 3)
    print("Fats " + str(round(fats, 2)), "Carbs " + str(round(carbs, 2)), "Protein " + str(round(protein,2)))
    return


macros()
