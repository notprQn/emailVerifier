## Verificador de Registros de Domínio

Este é um programa simples em Go que verifica a presença de registros MX, SPF e DMARC de um domínio fornecido pelo usuário.

### Funcionamento

1. O programa solicita ao usuário que insira um domínio.
2. Em seguida, verifica se o domínio tem registros MX (Mail Exchange), SPF (Sender Policy Framework) e DMARC (Domain-based Message Authentication, Reporting, and Conformance).
3. Os resultados são exibidos na tela, indicando se o domínio possui registros MX, SPF e DMARC, junto com os próprios registros, se aplicável.

### Requisitos

Certifique-se de ter Go instalado em seu sistema. Você pode encontrar instruções de instalação [aqui](https://golang.org/doc/install).

### Como Usar

1. Clone este repositório:

   ```
   git clone https://github.com/notprQn/emailVerifier.git
   ```

2. Navegue até o diretório clonado:

   ```
   cd verificador-de-registros-de-dominio
   ```

3. Execute o programa:

   ```
   go run main.go
   ```

4. Insira o domínio que deseja verificar quando solicitado.

### Estrutura do Código

- `main.go`: Contém o código principal que solicita o domínio ao usuário, chama a função `checkDomain()` e imprime os resultados.
- `README.md`: Esta documentação.

### Pacotes Importados

- **bufio**: Para leitura de entrada do usuário.
- **fmt**: Para formatação de saída.
- **log**: Para registro de erros.
- **net**: Para realizar a pesquisa DNS de registros MX, TXT e DMARC.
- **os**: Para acesso ao fluxo de entrada padrão.

### Variáveis Utilizadas

- **hasMX**: Indica se o domínio possui registros MX.
- **hasSPF**: Indica se o domínio possui registros SPF.
- **hasDMARC**: Indica se o domínio possui registros DMARC.
- **spfRecord**: Armazena o registro SPF do domínio.
- **dmarcRecord**: Armazena o registro DMARC do domínio.

### Funcionalidades

- **net.LookupMX()**: Pesquisa registros MX de um domínio.
- **net.LookupTXT()**: Pesquisa registros TXT de um domínio (utilizado para SPF e DMARC).
- **strings.HasPrefix()**: Verifica se uma string começa com o prefixo especificado.

### Saída

A saída exibe os seguintes campos para cada domínio fornecido:

- **domain**: O próprio domínio.
- **hasMX**: Se o domínio possui registros MX.
- **hasSPF**: Se o domínio possui registros SPF.
- **spfRecord**: O registro SPF do domínio (se presente).
- **hasDMARC**: Se o domínio possui registros DMARC.
- **dmarcRecord**: O registro DMARC do domínio (se presente).

### Tratamento de Erros

Erros são registrados utilizando o pacote `log`. Em caso de falha na busca de registros MX, TXT ou DMARC, o erro é exibido na saída padrão.
