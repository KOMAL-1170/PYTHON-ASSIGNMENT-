#Q1
# Initial list
L = [11, 12, 13, 14]

# (i) Add 50 and 60 to L
L.append(50)
L.append(60)
print("After adding 50 and 60:", L)

# (ii) Remove 11 and 13 from L
L.remove(11)
L.remove(13)
print("After removing 11 and 13:", L)

# (iii) Sort L in ascending order
L.sort()
print("Sorted in ascending order:", L)

# (iv) Sort L in descending order
L.sort(reverse=True)
print("Sorted in descending order:", L)

# (v) Search for 13 in L
if 13 in L:
    print("13 is found in L.")
else:
    print("13 is not found in L.")

# (vi) Count the number of elements in L
print("Number of elements in L:", len(L))

# (vii) Sum all the elements in L
print("Sum of all elements in L:", sum(L))

# (viii) Sum all ODD numbers in L
odd_sum = sum(x for x in L if x % 2 != 0)
print("Sum of odd numbers in L:", odd_sum)

# (ix) Sum all EVEN numbers in L
even_sum = sum(x for x in L if x % 2 == 0)
print("Sum of even numbers in L:", even_sum)

# (x) Sum all PRIME numbers in L
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(n**0.5)+1):
        if n % i == 0:
            return False
    return True

prime_sum = sum(x for x in L if is_prime(x))
print("Sum of prime numbers in L:", prime_sum)

# (xi) Clear all the elements in L
L.clear()
print("List after clearing:", L)

# (xii) Delete L
del L
# print(L)  # This would raise a NameError if uncommented

#Q2
# Initial dictionary
D = {1: 5.6, 2: 7.8, 3: 6.6, 4: 8.7, 5: 7.7}

# (i) Add new entry in D; key=8 and value=8.8
D[8] = 8.8
print("After adding key=8:", D)

# (ii) Remove key=2
if 2 in D:
    del D[2]
print("After removing key=2:", D)

# (iii) Check whether key=6 is present in D
if 6 in D:
    print("Key 6 is present in D.")
else:
    print("Key 6 is not present in D.")

# (iv) Count the number of elements present in D
print("Number of elements in D:", len(D))

# (v) Add all the values present in D
print("Sum of all values in D:", sum(D.values()))

# (vi) Update the value of key=3 to 7.1
D[3] = 7.1
print("After updating key=3 to 7.1:", D)

# (vii) Clear the dictionary
D.clear()
print("Dictionary after clearing:", D)

#Q3
# Define sets (converting from lists)
S1 = set([10, 20, 30, 40, 50, 60])
S2 = set([40, 50, 60, 70, 80, 90])

# (i) Add 55 and 66 in Set S1
S1.add(55)
S1.add(66)
print("S1 after adding 55 and 66:", S1)

# (ii) Remove 10 and 30 from Set S1
S1.discard(10)
S1.discard(30)  # discard doesn't raise error if item not found
print("S1 after removing 10 and 30:", S1)

# (iii) Check whether 40 is present in S1
if 40 in S1:
    print("40 is present in S1.")
else:
    print("40 is not present in S1.")

# (iv) Find the union between S1 and S2
union_set = S1.union(S2)
print("Union of S1 and S2:", union_set)

# (v) Find the intersection between S1 and S2
intersection_set = S1.intersection(S2)
print("Intersection of S1 and S2:", intersection_set)

# (vi) Find the difference S1 - S2
difference_set = S1.difference(S2)
print("S1 - S2:", difference_set)
#Q4
import random
import string

for _ in range(100):
    length = random.randint(6, 8)
    rand_str = ''.join(random.choices(string.ascii_letters + string.digits, k=length))
    print(rand_str)

def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

for num in range(600, 801):
    if is_prime(num):
        print(num)
for num in range(100, 1001):
    if num % 7 == 0 and num % 9 == 0:
        print(num)
#Q5
import random

# Create two lists of 10 random numbers between 10 and 30
list1 = [random.randint(10, 30) for _ in range(10)]
list2 = [random.randint(10, 30) for _ in range(10)]

print("List 1:", list1)
print("List 2:", list2)

# (i) Common numbers in the two lists
common = list(set(list1) & set(list2))
print("Common numbers:", common)

# (ii) Unique numbers in both the lists (symmetric difference)
unique = list(set(list1) ^ set(list2))
print("Unique numbers in both lists:", unique)

# (iii) Minimum in both lists
print("Minimum in List 1:", min(list1))
print("Minimum in List 2:", min(list2))

# (iv) Maximum in both lists
print("Maximum in List 1:", max(list1))
print("Maximum in List 2:", max(list2))

# (v) Sum of both the lists
print("Sum of List 1:", sum(list1))
print("Sum of List 2:", sum(list2))
#Q6
import random

# Function to check if a number is prime
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

# Create list of 100 random numbers between 100 and 900
numbers = [random.randint(100, 900) for _ in range(100)]
print("Random Numbers:\n", numbers)

# (i) All odd numbers
odd_numbers = [num for num in numbers if num % 2 != 0]
print("\nOdd Numbers:", odd_numbers)
print("Count of Odd Numbers:", len(odd_numbers))

# (ii) All even numbers
even_numbers = [num for num in numbers if num % 2 == 0]
print("\nEven Numbers:", even_numbers)
print("Count of Even Numbers:", len(even_numbers))

# (iii) All prime numbers
prime_numbers = [num for num in numbers if is_prime(num)]
print("\nPrime Numbers:", prime_numbers)
print("Count of Prime Numbers:", len(prime_numbers))
#Q7
# Define the dictionary
D = {1: "One", 2: "Two", 3: "Three", 4: "Four", 5: "Five"}

# Open a file to write
with open("dictionary_output.txt", "w") as file:
    for key, value in D.items():
        file.write(f"{key}, {value}\n")

print("Dictionary written to 'dictionary_output.txt' successfully.")
#Q8
# Define the list
L = ["One", "Two", "Three", "Four", "Five"]

# Open a file for writing
with open("length_output.txt", "w") as file:
    for word in L:
        file.write(f"{word}, {len(word)}\n")

print("Lengths written to 'length_output.txt' successfully.")
#Q9
import random
import string

# Open the file for writing
with open("random_strings.txt", "w") as file:
    for _ in range(100):
        length = random.randint(10, 15)
        rand_str = ''.join(random.choices(string.ascii_letters + string.digits, k=length))
        file.write(rand_str + "\n")

print("100 random strings written to 'random_strings.txt'.")
#Q10
# Function to check if a number is prime
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

# Open the file for writing
with open("prime_600_800.txt", "w") as file:
    for num in range(600, 801):
        if is_prime(num):
            file.write(str(num) + "\n")

print("Prime numbers between 600 and 800 written to 'prime_600_800.txt'.")
#Q11
import time

# Start the timer
start_time = time.time()

# Example code block (e.g., sum of first 1 million numbers)
total = 0
for i in range(1, 1000001):
    total += i

# End the timer
end_time = time.time()

# Calculate elapsed time
elapsed_time = end_time - start_time
print(f"Time taken by the program: {elapsed_time:.4f} seconds")
#12
import random
import time
import matplotlib.pyplot as plt

# Define the sizes of the lists
sizes = [5000, 10000, 15000, 20000, 25000]
times = []

# Measure time taken to sort lists of different sizes
for size in sizes:
    numbers = [random.randint(1, 1000000) for _ in range(size)]
    
    start_time = time.time()
    sorted_numbers = sorted(numbers)
    end_time = time.time()

    elapsed_time = end_time - start_time
    times.append(elapsed_time)
    print(f"Sorted {size} elements in {elapsed_time:.4f} seconds")

# Plotting the graph
plt.figure(figsize=(8, 5))
plt.plot(sizes, times, marker='o', linestyle='-', color='blue')
plt.title('List Size vs Time Taken to Sort')
plt.xlabel('Number of Elements in List')
plt.ylabel('Time Taken (seconds)')
plt.grid(True)
plt.tight_layout()
plt.show()
#13
# Dictionary of students and their marks in 5 subjects
students = {
    "Alice": [85, 78, 92, 88, 76],
    "Bob": [72, 68, 75, 70, 69],
    "Charlie": [90, 95, 93, 89, 94],
    "Diana": [60, 65, 58, 62, 64],
    "Ethan": [80, 82, 85, 79, 83]
}

# Dictionary to store averages
averages = {}

# Calculate average for each student
for name, marks in students.items():
    avg = sum(marks) / len(marks)
    averages[name] = avg

# Find student with max and min average
max_student = max(averages, key=averages.get)
min_student = min(averages, key=averages.get)

print(f"Student with Maximum Average: {max_student} ({averages[max_student]:.2f})")
print(f"Student with Minimum Average: {min_student} ({averages[min_student]:.2f})")
