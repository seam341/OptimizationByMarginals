def retrieve():
    input_type = input('What is the kind of input you are using the increase production? ')
    input_type = input_type.lower()
    min = int(input('What is the minimum amount of ' + input_type + ' that can be used during production? '))
    max = int(input('What is the maximum amount of ' + input_type + ' that can be used during production? '))
    increment = int(input('And how many of this input can be added or removed during production? '))
    print()

    return input_type, min, max, increment


def totalbuild(min, max, increment):
    total_cost = int(((1 + max - min)/increment)) * [0]
    total_rev = int(((1 + max - min) / increment)) * [0]

    index = 0
    while index < len(total_cost):
        total_cost[index] = int(input('What is the total cost of producing ' + str(min + index*increment) + ' units? '))
        total_rev[index] = int(input('What is the total revenue of producing ' + str(min + index*increment) + ' units? '))
        index += 1
    print()

    return total_cost, total_rev


def marginalbuild(total_cost, total_rev):
    marginal_cost = (len(total_cost) - 1) * [0]
    marginal_rev = (len(total_rev) - 1) * [0]

    index = 0
    while index < int(len(marginal_cost)):
        marginal_cost[index] = total_cost[index + 1] - total_cost[index]
        marginal_rev[index] = total_rev[index + 1] - total_rev[index]
        index += 1

    return marginal_cost, marginal_rev


def optimum(marginal_cost, marginal_rev, min, increment):
    index = 0
    while index < int(len(marginal_cost)):
        if marginal_cost[index] != marginal_rev[index]:
            index += 1
        else:
            index += 1
            print('The optium amount of production occurs at ' + str((index * increment) + min) + ' units of input.')

def main():
    itype, min, max, incr = retrieve()
    tc, tr = totalbuild(min, max, incr)
    mc, mr = marginalbuild(tc, tr)
    optimum(mc, mr, min, incr)

main()
