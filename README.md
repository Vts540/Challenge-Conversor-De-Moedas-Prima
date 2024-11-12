# Challenge-Conversor-De-Moedas-Prima

Conversor de Moedas
Este projeto é um Conversor de Moedas desenvolvido em Java, utilizando também a Biblioteca GSON  convertida para  JSON (JavaScript Object Notation) que é um formato de dados que permite a troca de informações entre sistemas computacionais. Este Conversor permite aos usuários converter entre diferentes moedas em tempo real. As cotações são atualizadas automaticamente por meio da integração com a API Exchange Rate API.
Funcionalidades
O conversor oferece as seguintes operações:
1.	Conversão de Dólar para Peso Argentino.
2.	Conversão de Peso Argentino para Dólar.
3.	Conversão de Dólar para Real Brasileiro.
4.	Conversão de Real Brasileiro para Dólar.
5.	Conversão de Dólar para Peso Colombiano.
6.	Conversão de Peso Colombiano para Dólar.
7.	Sair.
Como Usar
1.	Ao iniciar o programa, o usuário verá um menu com as opções de conversão.
2.	Basta inserir o número correspondente à operação desejada.
3.	Em seguida, insira o valor que deseja converter.
4.	O programa exibe o valor convertido, com base na taxa de câmbio atual fornecida pela API.
Exemplo do Código
Abaixo, o trecho principal do código que configura o menu de opções e realiza as conversões:
java
Copiar código
// Exemplo simplificado de inicialização
Scanner scanner = new Scanner(System.in);
ExchangeRateService exchangeRateService = new ExchangeRateService();

// Exibe menu e realiza operações
System.out.println("Escolha uma opção: ");
int opcao = scanner.nextInt();
// Tratamento de exceções e chamada da API para conversão...


Dependências e Configuração
Para utilizar a aplicação, é necessário ter uma chave de API do Exchange Rate API. Defina a chave no arquivo ExchangeRateService para garantir o funcionamento correto.
No caso, já deixarei minha chave juntamente do código para posterior utilização.
Dependências
Este projeto utiliza a biblioteca Gson para o parsing de JSON. Certifique-se de adicionar gson ao seu Programa para posterior utilização não só neste projeto quanto em futuros projetos. 
Estrutura da Classe de Serviço
A classe ExchangeRateService é responsável por conectar-se à API de taxas de câmbio e obter as taxas atuais para moedas específicas. Ela oferece o método principal obterTaxaCambio, que realiza a conversão entre duas moedas, garantindo que a taxa esteja disponível e tratando erros de conexão e de formato da resposta.
Exemplo de uso:
java
Copiar código
ExchangeRateService exchangeRateService = new ExchangeRateService();
double taxaCambio = exchangeRateService.obterTaxaCambio("USD", "BRL");
Cada conversão possui uma classe dedicada, o que permite fácil manutenção e expansibilidade do sistema.
Exemplo: Conversão de Dólar para Real Brasileiro
java
Copiar código
public class ConversaoDolarRealBrasileiro implements Conversao {
    private final double taxaCambio;

    public ConversaoDolarRealBrasileiro(double taxaCambio) {
        this.taxaCambio = taxaCambio;
    }

    @Override
    public double converter(double valor) {
        return valor * taxaCambio;
    }
}
Essa organização modular permite adicionar novas moedas apenas criando novas classes que implementem a interface Conversao e recebam uma taxa de câmbio.
Espero que apreciem o programa, eu o fiz não somente por conta do Challenge da Alura, porém também para recurso e utilização para me desenvolver melhor como  Profissional que busca sempre melhorar.

Obrigado  :)

