# Nesting-Tuple
def incr_dict(dct, tuples):

    if len(tuples) == 0:
        print(dct) 
        return

    dicts = dct

    for i in range(len(tuples)):
        if i == len(tuples)-1:
        # to get to last value in tuple
            if i in dicts:

            #increment or give value of 1

                dicts[tuples[i]]+=1
            else:
                dicts[tuples[i]]=1
            break

            #nesting so it wont matter if same key comes twice e.g. 'c' in tests

        elif tuples[i] in dicts:
            if type(dicts[tuples[i]]) is int:
                dicts[tuples[i]] = {}
            dicts = dicts[tuples[i]]
        else:
            dicts[tuples[i]] = {}
            dicts = dicts[tuples[i]]
    print(dct)
    
dct = {}

# Tests
incr_dict(dct, ('a', 'b', 'c'))
incr_dict(dct, ('a', 'b', 'c', 'd', 'e', 'g', 'h', 'i', 'j'))
incr_dict(dct, ('a', 'b', 'c', 'd', 'e', 'g', 'h', 'i', 'c'))
