# Projeto Final DMSN 

Desenvolvedor: Henrique Hamaguchi
Data da criação do documento: 21/12/2018
Data da última revisão do documento: 24/12/2018

1. Projeto: Através de um algoritmo de Machine Learning (ML) predizer se uma pessoa é de esquerda, direita ou neutra analisando os últimos posts no Twitter das pessoas.

2. Requisitos do projeto:
 Software: Programa Python 3 do Google Colab
 Bibliotecas:
    a. NumPy: o pacote básico da linguagem Python que permite trabalhar com arranjos, vetores e matrizes de N dimensões;
    b. SciPy: biblioteca fundamental para computação científica;
    c. Pandas: fornece ferramentas para análise e estrutura de dados;
    d. Scikit-Learn : biblioteca Python para trabalhar com Machine Learn (Aprendizado de Máquina);
    e. Twithon: fornece fácil acesso aos dados do Twitter.
 Arquivos:
    a. Projeto_DMSN.ipynb: localizado no Google Colab, no diretório My Drive/Colab Notebooks e tem uma versão disponível no GitHub;
    b. twitter_politico: spreadsheet localizada no Gooogle Drive, no diretório My Drive, e tem uma versão disponível no GitHub.
 Sistemas:
    a. Acesso ao Google Drive;
    b. Credenciais de acesso ao Twitter como desenvolvedor.
 Hardware: 
    Não tem, uma vez que o Google Colba roda o Python remotamente.

3. Como rodar o programa:   
 a. Carregar o código Projeto_DMSN.ipynb no Google Colab;
 b. Carregar a spreadshet no Google Drive. Vale a ressalva que esse documento precisa ter ter sheets criadas previamente para funcionar;
 c. Por fim, executar o código no Google Colab.
  
 4. Algoritmo utilizado: Classificador Naive Bayes Multinomial
 Motivo: uma vez que realizo uma classificação do twittes em direita, esquerda ou neutro, e pretendo utilizar esta informação (variável alvo) para um treinamento supervivionado,o classificador mostra-se uma possível solução. Em particular será adotado o classificador de Naive Bayes. O classificador de Naive Bayes assume que a presença de uma característica particular em uma classe não está relacionada com a presença de qualquer outra característica (regra de independência), o que simplifica o problema. De qualquer forma os classificadores Naive Bayes são muito utilizados em classificação de textos e costumam performar melhor que outras técnicas mais complexas. E explicando a última escolha do classificador, o "multinomial", é que ele considera quantas vezes uma determindada palavra apareceu no twittes, em contrapartida, por exemplo, o modelo de Bernoulli considera apenas o fato se uma determinada palavra apareceu ou não nos twittes.

 Limitações:
 a. O classificador está é muito sensível ao treinamento, se no treinamento uma palavra está em um dos twittes que eu classifiquei como "direita", essa mesma palavra pode aparecer num twitter com contexto de esquerda e classificar errado. Exemplo:  . 
 b. Ao selecionar mais que 100 twittes para cada classificar, eu estava tendo um problema sistêmico de estouro de memória no Google Colab;
 c. O categoria neutra dificilmente é identificada, creio que pelo fato de que há necessidade de realizar um treinamento mais efetivo, de forma que se tire os twittes de direita e esquerda e quaisquer twittes relacionados a política.
 
 Propostas de Melhorias:
 a. Definir melhor o que seria as palavras chaves para direita, esquerda e neutro;
 b. O classificador deveria ser treinado com uma amostra maior;
 c. Realizar uma limpeza nos twittes, alguns aparecem várias vezes e tem muitas palavras (conjunções, preposições) que não agregam para o classificador.

 5. Proposta de melhoria do projeto;
 O projeto poderia ser quebrado em funções:
    a. função de captura_twitter
        inputs: usuario, twittes
        output: classificação dos twittes (0 - direita,1 - esquerda,2 -neutro)
    b. função que armazenasse o classificador treinado
