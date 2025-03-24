# Lista de Exercícios 1

1. Protocolos HTTP, HTTPS, TCP, IP e DNS.
    - O protocolo HTTP é um protocolo de comunicação entre cliente-servidor para a transferência de dados. Define verbos para requisições e padroniza requisições e respostas com códigos de estado.
    - O protocolo HTTPS é a versão segura do HTTP, que utiliza criptografia TLS/SSL para proteger os dados transmitidos entre cliente e servidor.
    - O protocolo TCP é um protocolo de transporte confiável, que garante a entrega ordenada e sem erros dos pacotes de dados​. 
    - O protocolo IP é responsável pelo roteamento e endereçamento dos pacotes de dados na rede, garantindo que eles cheguem ao destino correto.
    - O protocolo DNS converte nomes de domínio em endereços de IP, permitindo que os navegadores encontrem os servidores corretos.
<br>
2. A arquitetura cliente-servidor, ou requisição-resposta, é o modelo fundamental da web, onde  um cliente, geralmente um navegador, solicita recursos a um servidor.
    O cliente inicia a comunicação enviando uma requisição HTTP/HTTPS, que pode ser uma página, uma imagem ou dados de uma API. Antes de enviar a requisição ao servidor, o navegador precisa obter o endereço IP do site, o que é feito por meio de uma consulta ao DNS. Com o endereço obtido, a requisição HTTP ou HTTPS é enviada ao servidor, pedindo o recurso desejado.
    O servidor recebe a requisição, processa e retorna uma resposta HTTP, contendo os dados solicitados e um código de status (como 200 OK ou 404 Not Found).
    O cliente interpreta a resposta e exibe o conteúdo. Se forem necessários outros recursos, faz novas requisições ao servidor.
<br>
3. O protocolo HTTP define uma série de interfaces para requisição e resposta. A requisição é padronizada por meio de verbos: POST, GET, PUT, DELETE, PATCH, etc. A resposta também é padronizada por meio de código de resposta ou códigos de estados.
    Uma requisição HTTP contém alguns elementos básicos:
    -  Os dados da requisição que contém a versão HTTP utilizada, a URL referente à solicitação HTTP e o método que indica a ação principal que será utilizada por aquela requisição. 
    - O cabeçalho HTTP, que contém os dados sobre o navegador, cookies e tipo de dado solicitado.
    - O corpo HTTP, que é opcional, incorpora informações necessárias para o cumprimento da solicitação.
<br>
4. 
    **a)** O método GET solicita dados do servidor, enviando informações anexadas à URL por meio de query strings. Ele não altera o estado do servidor, pode ser armazenado em cache e no histórico do navegador. No entanto, a URL tem limite de tamanho, restringindo a quantidade de dados enviados.
    O método POST envia dados ao servidor pelo corpo da requisição, permitindo grandes volumes de informação. Como não é idempotente, requisições repetidas podem gerar resultados diferentes. Além disso, oferece mais segurança para dados sensíveis, pois não os expõe na URL.
    O método DELETE remove recursos no servidor e é idempotente, ou seja, requisições repetidas não causam mudanças adicionais. Os dados para exclusão são passados na URL ou nos cabeçalhos, sem corpo na requisição. Além disso, não deve ser armazenado em cache para garantir a execução da exclusão.
    <br>
    **b)** HTTP 100 Continue -> Indica que o servidor recebeu a parte inicial da requisição e o cliente pode continuar enviando o restante. Por exemplo, quando um cliente envia uma requisição com um header Expect: 100-continue, aguardando confirmação antes de enviar um corpo grande de dados.
    HTTP 200 OK -> Indica que a solicitação foi bem-sucedida. Por exemplo ao acessar uma página da web com sucesso.
    HTTP 301 Moved Permanently -> Indica que o recurso foi movido para uma nova URL de forma permanente. Por exemplo, quando um site muda de domínio e redireciona os usuários para o novo endereço.
    HTTP 404 Not Found -> Ocorre quando o servidor não encontra o recurso solicitado. Por exemplo, ao tentar acerssar uma URL inexistente.
    HTTP 500 Internal Server Error -> Indica erro interno no servidor que o impede de processar a requisição. Por exemplo, falha ao executar um script no servidor.
<br>
5.  Para contornar a restrição de que o servidor não pode enviar dados sem uma requisição explícita do cliente, pode-se utilizar as seguintes estratégias:
    - Polling de espera, que consiste em o cliente realizar requisições periódicas ao servidor para verificar novas informações, mas pode gerar alto consumo de recursos e tráfego desnecessário. 
    - WebSockets, que estabelecem uma comunicação bidirecional em tempo real, mantendo uma conexão persistente, o que permite ao servidor enviar dados ao cliente sem necessidade de novas requisições. 
    - APIs AJAX Avançadas, que facilitam a comunicação assíncrona e possibilitam atualizações dinâmicas sem recarregar a página. 
    - Server-Sent Events (SSE) permite que o servidor mantenha uma conexão aberta e envie eventos contínuos ao cliente sempre que houver novas informações. Diferente dos WebSockets, o SSE é unidirecional, permitindo apenas o envio de dados do servidor para o cliente.
    