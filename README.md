def saisir ():
    try:
        x=int(input('donner votre choix'))
        if x in [1,2,3,4,5]:
            return(x)
    except ValueError:
        print('se caractere n''est pas dans notre choix')
        saisir()
def verifier ():
    try:
        x=int(input('voulez vous vraiment supprimer ce contact'))
        if x in ['S','N']:
            return(x)
    except ValueError:
        print('se caractere n''est pas dans notre choix')
        verifier()
def menu():
    import os
    print('*****************************************************')
    print('                    menu                            ')
    print('*            1-Ajouter un contact                   *')
    print('*            2-Modifier un contact                  *')
    print('*            3-Supprimer un contact                 *')
    print('*            4-Afficher tous les contact            *')
    print('*            5-Afficher un contact                  *')
    print('*****************************************************')
    x=saisir()
    if x==1:
        system.os('cls')
        import os
        dict={}
        dict[nom]=input('donner un nom')
        dict[prenom]=input('donner un prenom')
        dict[num_tel]=input('donner un num_tel')
        dict[adress]=input('donner une adress')
        dict[mail]=input('donner un mail')
        fs=open('contacts.txt','a+')
        fs.write(str(dict))
        fs.close()
        system.os('cls')
        import os
        print('*****************************************************')
        print('                      ajouter un contact             ')
        print('nom:',dict['nom'])
        print('prenom:',dict[prenom])
        print('num_tel:',dict[num_tel])
        print('adress:',dict[adress])
        print('mail:',dict[mail])
        print('*****************************************************')
        system.os('cls')
        v = input('tapez 0 si vous voulez retournez au menu')
        if v == 0:
            menu()
    elif x==2:
        system.os('cls')
        y=input('donner le numero a modifier')
        fs=open('contacts.txt', 'r+')
        for dict in fs:
            if dict[num_tel]==y:
                dict={}
                dict[nom] = input('donner un  nom')
                dict[prenom] = input('donner un prenom')
                dict[num_tel] = input('donner un num_tel')
                dict[adress] = input('donner une adress')
                dict[mail] = input('donner un mail')
                fo.open('contacs.txt','a+')
                fo.write(str(dict))
                fo.close()
                fs.close()
                import os
                print('*****************************************************')
                print('                      modifier un contact             ')
                print('nouveau nom:', dict['nom'])
                print('nouveau prenom:', dict[prenom])
                print('nouveau num_tel:', dict[num_tel])
                print('nouvelle adress:', dict[adress])
                print('nouveau mail:', dict[mail])
                print('*****************************************************')
                system.os('cls')
                v = input('tapez 0 si vous voulez retournez au menu')
                if v == 0:
                    menu()
        else:
            v = input('tapez 0 si vous voulez retournez au menu')
            if v == 0:
                menu()
    elif x==3:
        system.os('cls')
        y=input('donner le numero a modifier')
        fs=open('contacts.txt', 'r+')
        for dict in fs:
            if dict[num_tel]==y:
                import os
                print('*****************************************************')
                print('                      supprimer un contact             ')
                print('contact num a supprimer:',dict[num_tel])
                print('nouveau nom:', dict['nom'])
                print('nouveau prenom:', dict[prenom])
                print('nouveau num_tel:', dict[num_tel])
                print('nouvelle adress:', dict[adress])
                print('nouveau mail:', dict[mail])
                print('*****************************************************')
                system.os('cls')
                z=verifier()
                if z=='S':
                    dict.pop()
                    fs.close()
                    v=input('tapez 0 si vous voulez retournez au menu')
                    if v==0:
                        menu()
                else:
                    fs.close()
                    v = input('tapez 0 si vous voulez retournez au menu')
                    if v == 0:
                        menu()
        else:
            menu()
    elif x==4:
        fs=open('contacts.txt','r')
        i=0
        for dict in fs:
            i=i+1
            print('*****************************************************')
            print('                      afficher les  contact             ')
            print('contact:',i)
            print(' nom:', dict['nom'])
            print(' prenom:', dict[prenom])
            print(' num_tel:', dict[num_tel])
            print(' adress:', dict[adress])
            print(' mail:', dict[mail])
            print('*****************************************************')
        fs.close()
        v = input('tapez 0 si vous voulez retournez au menu')
        if v == 0:
            menu()
    elif x==5:
        y=input('donner le numero du contact')
        fs=open('contacts.txt','r+')
        for dict in fs:
            if dict[num_tel]==y:
                print(fs.read(str(dict)))
                v = input('tapez 0 si vous voulez retournez au menu')
                if v == 0:
                    menu()
        else:
            menu()
