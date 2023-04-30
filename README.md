# AVC_class
## Introdução
O projeto AVC_class procurava fazer um estudo sobre os fatores de risco para apresentar um AVC, além de ser capaz de fazer uma predição se determinada pessoa apresentaria tal acidente ou não com base em suas características pessoais. Inicialmente, possuíamos um banco de dados contendo informações de pessoas com e sem AVC, além de informações pessoais, como por exemplo gênero, idade, doenças, etc.

## Como instalar
Para utilizar o programa basta clonar esse repositório em algum local de sua máquina. Para fazer isso, clique no botão verde **"Code"** logo acima, escolha um modo de baixar o repositório, podendo ser baixando o zip e descompactando ou clonando através de https ou ssh. Após seguir essas etapas, será preciso instalar as bibliotecas necessárias. Isso pode ser feito, estando na raiz do projeto, rodando no terminal o seguinte comando:  `pip install -r requirements.txt `, com isso, as bibliotecas necessárias serão instaladas.

## Teoria/Modelo matemático
Separamos o nosso banco de dados em dois dataframes, um contendo a informação se determinada pessoa possui ou não AVC (y), enquanto o outro apresenta todas as características que podem (ou não) influenciar o acidente, ou seja, as ‘features’ (X).\
Para aplicar o nosso estudo, separamos os dados em dados de teste (X_test e y_test) e de treino (X_train e y_train), sendo metade para cada conjunto. Com o ambiente configurado, utilizamos regressão linear definindo uma função de perda, uma matriz w que define a relevância de cada uma das features para determinar se a pessoa teria AVC ou não, e um valor b (bias), também utilizamos a biblioteca autograd (função grad) para calcular o gradiente da função de perda. Dessa forma conseguimos gradualmente diminuir o nosso erro enquanto recalculamos o nosso ‘w’ e o ‘b’  com base em suas derivadas parciais, até que ele apresentasse um valor de erro aceitável (menor erro). Tal procedimento foi executado durante 50 mil iterações.\
<img src= "https://github.com/eriksoaress/AVC_class/blob/main/erros_200mil_interac.png">\
A partir do gráfico gerado acima conseguimos perceber que a partir de um valor próximo a 50 mil, o nosso erro passa a se manter quase constante, por isso, por mais que aumentamos o número das iterações, o erro continuaria praticamente igual. Sendo assim, calculamos o nosso “w” e “b” para 50 mil iterações somente.\
Com o modelo treinado (w e b finais), nós utilizamos os nossos dados de teste para ver qual acurácia seria obtida, chegando a um valor próximo a 75%. Também criamos uma hipótese nula, que é um modelo que sempre chuta (sem critérios) no resultado mais recorrente, comparamos ambos os modelos e percebemos que o nosso foi superior em cerca de 25 pontos percentuais.
## Conclusão
Com base no w obtido, foi possível concluir seguindo o no nosso modelo, que os principais fatores de risco para o AVC estão relacionados a hipertensão e ao tabagismo. Isso é bastante interessante e esperado, haja vista que é de conhecimento que esses são de fato causas comuns para o AVC, assim como é exposto no artigo "Investigação Etiológica do Acidente Vascular Cerebral no Adulto Jovem" e "Perfil epidemiológico dos idosos acometidos por acidente vascular cerebral".

Fontes Bibliográficas:
https://revista.spmi.pt/index.php/rpmi/article/view/482
https://dialnet.unirioja.es/servlet/articulo?codigo=6771953