# leesanmath
def check_reflexive(R):
    elements = {x for pair in R for x in pair}
    for element in elements:
        if (element, element) not in R:
            return False
    return True

def check_symmetric(R):

    for pair in R:
        if (pair[1], pair[0]) not in R:
            return False
    return True

def check_transitive(R):
    for x in R:
        for y in R:
            if x[1] == y[0] and (x[0], y[1]) not in R:
                return False
    return True

def check_equivalence(R):
    if not check_reflexive(R):
        return False
    if not check_symmetric(R):
        return False
    if not check_transitive(R):
        return False
    return True
