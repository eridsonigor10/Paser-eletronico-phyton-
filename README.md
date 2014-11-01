Paser-eletronico-phyton-
========================
print(Autor: Eridson Igor Gomes da Silva)
print("             *******Parser*******              ")

s= raw_input("Insira os endereços eletronicos e pressione enter: ")

#Convertendo os (at) e [at] em @
s = s.replace("(at)","@")
s = s.replace("[at]","@")
alfabeto=['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z','0','1','2','3','4','5','6','7','8','9','_','-','.']
alfabeto2=['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z','A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z','0','1','2','3','4','5','6','7','8','9','_','-','.','@']
quant_arroba=s.count('@')
cont=0
pos_arroba=0
pos_i=0 #pos.delimitador antes do @
pos_x=0 #pos.delimitador depois do @
pos=0

#Passando pela string s
while (cont<quant_arroba):#para com o loop no maximo de numeros de @
    pos_arroba= s.find("@",pos_arroba) # procurando o @
    if pos_arroba != -1: #encontrou o @
        for i in s[pos_i:pos_arroba]:#passando pela fatia da string antes do @
            if (i in alfabeto) == False: #procurando delimitadores
                pos_i=s.find(i,pos,pos_arroba)#posição do delimitador  

    pos_ponto= s.find('.',pos_arroba) #procurando o ponto obrigatório apos o @
    if pos_ponto != -1:
        inv=s[::-1]
        for x in inv[:(pos_arroba-len(s))]: #passando pela fatia depois do @
            if (x in alfabeto2) == False: # procurando delimitador depois do @
                pos_x = s.find(x,(pos_arroba))
                
    else:
       print("Fim do programa")
        
    print(s[pos_i+1:pos_arroba]),
    print(s[pos_arroba:(pos_x)])
    pos_i+=1
    pos_arroba=pos_arroba+ 1 
    pos_x+=1
    pos=pos + len(s[pos_i+1:pos_x])
    cont+=1
