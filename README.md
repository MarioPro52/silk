# silkclass Silkworm:
    def __init__(self, name):
        self.name = name
        self.age = 0
        self.size = 'small'
        self.is_alive = True

    def grow(self):
        if self.is_alive:
            self.age += 1
            if self.age <= 3:
                self.size = 'small'
            elif self.age <= 6:
                self.size = 'medium'
            else:
                self.size = 'large'
        else:
            print(f"{self.name} is no longer alive.")

    def spin_cocoon(self):
        if self.is_alive and self.size == 'large':
            print(f"{self.name} is spinning a cocoon.")
            self.size = 'cocoon'
        else:
            print(f"{self.name} cannot spin a cocoon right now.")

    def die(self):
        if self.is_alive:
            print(f"{self.name} has died.")
            self.is_alive = False
        else:
            print(f"{self.name} is already dead.")


# Main program
if __name__ == "__main__":
    # Create a silkworm instance
    silkworm = Silkworm("Silky")

    # Simulate the life cycle
    for _ in range(10):
        silkworm.grow()
        if silkworm.age == 4:
            silkworm.spin_cocoon()
        print(f"{silkworm.name} is {silkworm.size}.")

    silkworm.die()
