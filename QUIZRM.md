import Foundation
pontos = 0
func trabalhar(pergunta: (enunciado: String, alternativas: (String, String, String), resposta: String)) {
    mostrar(pergunta: pergunta.enunciado)
    mostrar(altA: pergunta.alternativas.0, altB: pergunta.alternativas.1, altC: pergunta.alternativas.2)
    let palpite = coletarResposta()
    print("Você escolheu a alternativa... \(palpite)")
    print()

    if palpite.lowercased() == pergunta.resposta.lowercased() {
        print("Parabéns, você acertou!\n")
        pontos += 1
        print("Sua pontuação = \(pontos) ")
    } else {
        print("Não sabe, não sabe, vai ter que aprender...\n")
        }
    }


// mostrar a pergunta
func mostrar(pergunta: String) {
    print(pergunta)
    print("--------")
}

func mostrar(altA: String, altB: String, altC: String) {
    print("a. \(altA)")
    print("b. \(altB)")
    print("c. " + altC)
    print("--------\n")
}

func coletarResposta() -> String {
    print("Digite a alternativa correta e aperte enter!")
    let resposta = readLine()
    return resposta!
}

// score do jogo
var pontos = 0

// perguntas
var perguntas: [(enunciado: String, alternativas: (String, String, String), resposta: String)] = []



//hobbit
let alternativasHbt = ("Frodo", "Bilbo", "Sam")
perguntas.append((enunciado: "Qual o nome do Hobbit principal no filme: O Hobbit?", 
                  alternativas: alternativasHbt, resposta: "b"))

//hobbit
let alternativasHbb = ("As charadas", "A espada", "O anel")
perguntas.append((enunciado: "Em o Hobbit, qual o meio que Bilbo utiliza para fugir de Gollum?", alternativas: alternativasHbb, resposta: "c"))

// hobbit
let alternativasHobbit = ("13: 11 anões, 1 mago e 1 hobbit", "14: 11 anões, 1 mago e 2 hobbits", "15: 13 anões,1 mago e 1 hobbit")
perguntas.append((enunciado: "Em o Hobbit, quantos personagens saem numa jornada inesperada?", alternativas: alternativasHobbit, resposta: "c"))

// ramones
let alternativasSuits = ("Associado, sócio júnior, sócio nominal, sócio sênior e sócio gerente", "Associado, sócio nominal, sócio júnior, sócio gerente e sócio sênior", "Associado, sócio júnior, sócio sênior, sócio nominal e sócio gerente")
perguntas.append((enunciado: "Em Suits, qual a ordem correta da hierarquia da firma?", alternativas: alternativasSuits, resposta: "c"))

// pokemon
let alternativasSherlock = ("Moriarty", "Mycroft", "Irene Adler")
perguntas.append((enunciado: "Em Sherlock, quem afirma ser seu arqui-inimigo?", alternativas: alternativasSherlock, resposta: "b"))

let alternativasCab = ("Maria", "Sula", "Gil Marie")
perguntas.append((enunciado: "Quem é a melhor cabeleireira do Curado 1", alternativas: alternativasCab, resposta: "c"))




for pergunta in perguntas {
    trabalhar(pergunta: pergunta)
}

print("------")
print("JOGO TERMINADO!")
print("SUA PONTUAÇÃO FOI \(pontos)!")

switch pontos {
case 6:
    print ("DEU SHOW")
case 5:
    print("MANDOU BEM, ACERTOU TUDO!")
case 4:
    print("POR POUCO NÃO ARRASOU")
case 3:
    print("ATÉ LEGALZINHO")
case 2:
    print("PELO MENOS NÃO ERROU TUDO NÉ?!")
case 1:
    print("QUASE QUE ZERA!")
case 0:
    print("SABE DE NADA!!!")
default:
    print()
}

