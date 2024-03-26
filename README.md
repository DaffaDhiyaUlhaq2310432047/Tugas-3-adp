# Tugas-3-adp

def fibonacci(n):
    if n <= 2:
        return 1
    else:
        a, b = 1, 1
        for i in range(3, n + 1):
            temp = a + b
            a = b
            b = temp
        return b

def fibonacci_sum(n):
    total_sum = 0
    for i in range(1, n + 1):
        total_sum += fibonacci(i)
    return total_sum

while True:
    try:
        n = int(input("Masukkan nilai n (3 <= n <= 100 atau 109 <= n <= 199): "))
        if (3 <= n <= 100) or (109 <= n <= 199):
            fib_n = fibonacci(n)
            print("Bilangan Fibonacci ke-{}: {}".format(n, fib_n))
            sum_fib = fibonacci_sum(n)
            print("Jumlah deret Fibonacci hingga ke-{}: {}".format(n, sum_fib))
        else:
            print("Nilai n tidak memenuhi ketentuan.")
    except ValueError:
        print("Masukan tidak valid.")
    
    try:
        z = input("Apakah Anda ingin mencoba lagi? (y/n): ").lower()
        if z != 'y':
            break
    except ValueError:
        print("Masukan tidak valid.")
