# crosses
# My first repository GitHub

print('Крестики-нолики')
matrix = [[list(range(1, 10))[0+i*3], list(range(1, 10))[1 + i * 3], list(range(1, 10))[2 + i * 3]] for i in range(3)]
print(*matrix, sep='\n')

def field(a,b):
    for i in range(len(matrix)):
        for j in range(len(matrix)):
            if matrix[i][j]==a:
                matrix[i][j]=b
    print()
    print(*matrix , sep='\n')

used_cells=[]

def number_entry_x():
    while True:
        x = int(input('Необходимо ввести число от 1 до 9 для выбора позиции Вашего "X": '))
        if 1 <= x <= 9 and type(x) == int and x not in used_cells:
            used_cells.append(x)
            return field(x, 'X')
        else:
            print("Ввод неверен. Возможно Вы ввели повторное или неверное значение.")


def number_entry_y():
    while True:
        y = int(input('Необходимо ввести число от 1 до 9 для выбора позиции Вашего 0: '))
        if 1 <= y <= 9 and type(y) == int and y not in used_cells:
            used_cells.append(y)

            return field(y, 0)
        else:
            print("Ввод неверен. Возможно Вы ввели повторное или неверное значение.")


def entering_values():
    counter=0
    while True:
        if counter==9:
            return 'Ничья'
            break
        print(number_entry_x())
        counter += 1
        if matrix[0][0] == matrix[0][1] == matrix[0][2] or matrix[1][0] == matrix[1][1] == matrix[1][2] or matrix[2][
            0] == matrix[2][1] == matrix[2][2] \
                or matrix[0][0] == matrix[1][0] == matrix[2][0] or matrix[0][1] == matrix[1][1] == matrix[2][1] or \
                matrix[0][2] == matrix[1][2] == matrix[2][2] \
                or matrix[0][0] == matrix[1][1] == matrix[2][2] or matrix[0][2] == matrix[1][1] == matrix[2][0]:
            return 'Вы победитель X!!!'
        print(number_entry_y())
        counter += 1
        if matrix[0][0] == matrix[0][1] == matrix[0][2] or matrix[1][0] == matrix[1][1] == matrix[1][2] or matrix[2][
            0] == matrix[2][1] == matrix[2][2] \
                or matrix[0][0] == matrix[1][0] == matrix[2][0] or matrix[0][1] == matrix[1][1] == matrix[2][1] or \
                matrix[0][2] == matrix[1][2] == matrix[2][2] \
                or matrix[0][0] == matrix[1][1] == matrix[2][2] or matrix[0][2] == matrix[1][1] == matrix[2][0]:
            return 'Вы победитель 0!!!'


print(entering_values())
