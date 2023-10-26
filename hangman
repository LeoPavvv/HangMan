import random
from listado import posibilidades, letras

class Juego:
    
    def __init__(self):
        self.palabra = ""
        self.aux = ""
        self.aciertos = 0
        self.vidas = 7
        self.eleccion()
    
    def eleccion(self):
        self.palabra = posibilidades[random.randint(0,314)]
        self.aux = "_" * len(self.palabra) 

    def get_palabra(self):
        return self.palabra

    def oculto(self):
        print("_" * len(self.palabra))

    def validaciones(self, dato):
        x = ""
        if dato not in letras:
            x += " No puede ingresar un numero o simbolo"
        
        if len(dato) > 1:
            x += " No puede ingresar más de una letra"
        
        if(x != ""):
            print(x)
            return False
        
        else:
            return True
    
    def poner(self, x):
        aux_lista = list(self.aux) 
        for i in range(0, len(self.palabra)):
            if self.palabra[i] == x:
                aux_lista[i] = x
        self.aux = "".join(aux_lista)
        print(self.aux)

    def verificar(self, x):
        e = 0
        if x in self.palabra:
            for i in self.palabra:
                if i == x:
                    e += 1

            self.aciertos += e
            return True
        
        else:
            return False

    def letra(self):
        print("vidas:" , self.vidas)
        x = input("ingrese una letra: ")
        if self.validaciones(x):
            if self.verificar(x):
                print("Felicitaciones acertaste una letra")
                self.poner(x)

                if self.aciertos == len(self.palabra):
                    print("Felicidades!!! Has ganado")
                else:
                    return self.letra()

            else:
                print("La palabra no contiene esa letra")
                print(self.aux)
                self.vidas -=1

                if self.vidas == 0:
                    print("Perdiste. La palabra era", self.palabra)

                else:
                    return self.letra()

        else:
            return self.letra()

    def start():
        x = Juego()
        return x.jugar()

    def jugar(self):
        print(self.aux)
        self.letra()

Juego.start()
