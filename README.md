class City:
    def __init__(self, name, population=0, budget=1000, happiness=50):
        self.name = name
        self.population = population
        self.budget = budget
        self.happiness = happiness

    def build_residential_zone(self):
        cost = 200
        if self.budget >= cost:
            self.budget -= cost
            print("Budujesz nową dzielnicę mieszkalną.")
            self.population += 50
        else:
            print("Nie masz wystarczająco pieniędzy!")

    def build_commercial_zone(self):
        cost = 300
        if self.budget >= cost:
            self.budget -= cost
            print("Budujesz nową dzielnicę handlową.")
        else:
            print("Nie masz wystarczająco pieniędzy!")

    def build_industrial_zone(self):
        cost = 400
        if self.budget >= cost:
            self.budget -= cost
            print("Budujesz nową dzielnicę przemysłową.")
        else:
            print("Nie masz wystarczająco pieniędzy!")

    def build_public_service(self, service):
        costs = {"hospital": 500, "school": 400, "park": 300}
        if service in costs:
            cost = costs[service]
            if self.budget >= cost:
                self.budget -= cost
                print(f"Budujesz nowe {service}.")
            else:
                print("Nie masz wystarczająco pieniędzy!")
        else:
            print("Nieprawidłowy rodzaj usługi publicznej.")

    def collect_taxes(self):
        income = self.population * 10
        self.budget += income
        print(f"Zebrano podatki w wysokości {income}.")

    def check_happiness(self):
        if self.happiness > 70:
            print("Mieszkańcy są bardzo zadowoleni.")
        elif 50 <= self.happiness <= 70:
            print("Mieszkańcy są umiarkowanie zadowoleni.")
        else:
            print("Mieszkańcy są niezadowoleni. Musisz coś zrobić!")

# Przykładowe użycie:
my_city = City("Moje Miasto")
my_city.build_residential_zone()
my_city.build_commercial_zone()
my_city.build_public_service("school")
my_city.collect_taxes()
my_city.check_happiness()

