# Desafio-Greencode-1---Iniciante

Desenvolver um programa que solicite ao usuário o tipo de energia (eletricidade ou gás natural) e o respectivo consumo. Utilize fatores de emissão específicos para cada tipo de energia: Eletricidade (0.475 kg CO2/kWh) e gás natural (2.0 kg CO2/m³). O programa deve calcular a pegada de carbono para cada tipo de energia inserido e, ao final, apresentar o valor total da pegada de carbono.


fun main() {
    val emissao_eletricidade = 0.475
    val emissao_gas = 2.0
    var consumo_eletricidade: Double
    var consumo_gas: Double
    var total_eletricidade: Double
    var total_gas: Double
    var total_co2: Double

    while (true) { //loop while inicial para garantir que o usuario possa repetir ou sair do programa ao final da execução

        do { //Do-while para repetir a pergunta em caso de entradas inválidas
            println("Informe o consumo total de eletricidade em kWh/m³: ")
            consumo_eletricidade = readln().toDoubleOrNull() ?: -1.0 /* Elvis '?:' para setar um valor null em números negativos e melhorar o tratamento de dados?*
            if (consumo_eletricidade < 0) { // Rejeita valores negativos
                println("Valor inválido, digite apenas números positivos")
            }
        } while (consumo_eletricidade < 0)

        do { 
            println("Informe o consumo total de gás em kWh/m³: ")
            consumo_gas = readln().toDoubleOrNull() ?: -1.0
            if (consumo_gas < 0) {
                println("Valor inválido, digite apenas números positivos")
            }
        } while (consumo_gas < 0)

        total_eletricidade = consumo_eletricidade * emissao_eletricidade
        total_gas = consumo_gas * emissao_gas
        total_co2 = total_eletricidade + total_gas

        println("Eletricidade: ${total_eletricidade} kg CO2")
        println("Gás: ${total_gas} kg CO2")
        println("Total: ${total_co2} kg CO2")

        println("Deseja calcular novamente?")
        println("(1) - Sim (2) - Não")

        val resposta = readln().toInt()
        if (resposta != 1) { /* Encerra o loop inicial e o programa se o usuario entrar com um valor que não seja 1 */
            break
        }
    }
}

