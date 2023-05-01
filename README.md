# AVC_class
## Introdução
O projeto AVC_class procurava fazer um estudo sobre os fatores de risco para apresentar um AVC, além de ser capaz de fazer uma predição se determinada pessoa apresentaria tal acidente ou não com base em suas características pessoais. Inicialmente, possuíamos um banco de dados contendo informações de pessoas com e sem AVC, além de informações pessoais, como por exemplo gênero, idade, doenças, etc.

## Como instalar
Para utilizar o programa basta clonar esse repositório em algum local de sua máquina. Para fazer isso, clique no botão verde **"Code"** logo acima, escolha um modo de baixar o repositório, podendo ser baixando o zip e descompactando ou clonando através de https ou ssh. Após seguir essas etapas, será preciso instalar as bibliotecas necessárias. Isso pode ser feito, estando na raiz do projeto, rodando no terminal o seguinte comando:  `pip install -r requirements.txt `, com isso, as bibliotecas necessárias serão instaladas.

## Teoria/Modelo matemático
Para aplicar o estudo, separamos os dados em dados de teste e de treino. O modelo foi construído utilizando regressão linear, foi definido uma função de perda, uma matriz 'w' que define a relevância de cada uma das features para determinar se a pessoa teria AVC ou não, e um valor 'b' (bias), também calculamos o gradiente da função de perda. O objetivo do algoritmo utilizado para construir o modelo é minimizar a função de perda, ou seja, encontrar valores de w e b que minimizem a diferença entre as previsões do modelo e os valores reais.

Durante o treinamento, o algoritmo ajusta os valores de 'w' e 'b' usando o gradiente descendente (que calcula o gradiente da função de perda em relação aos parâmetros w e b) e, em seguida, ajusta esses parâmetros proporcionalmente ao gradiente, com uma taxa de aprendizagem determinada previamente.

O modelo, então, aprende a melhor combinação de valores de w e b para fazer previsões sobre os dados de entrada. Isso é possível porque a função de perda fornece uma medida de quão bem o modelo está fazendo previsões e como ajustar os valores para melhorar essas previsões.

Em outras palavras, o algoritmo ajusta os valores para minimizar a diferença entre as previsões do modelo e os valores reais a fim de maximizar a precisão do modelo.

<img src= "https://github.com/eriksoaress/AVC_class/blob/main/erros_200mil_interac.png">\
A partir do gráfico gerado acima percebemos que a partir de 50 mil, o nosso erro passa a se manter praticamente constante, por isso, mesmo aumentando as iterações o erro continuaria praticamente igual. Sendo assim, tal procedimento foi 50 mil vezes.\
Com o modelo treinado, nós utilizamos os dados de teste para ver a acurácia obtida, chegando a um valor superior a 70%. Também definimos uma hipótese nula, que é um modelo que sempre chuta no resultado mais recorrente, comparamos ambos os modelos e percebemos que o nosso foi superior em mais de 20%.
## Conclusão
Com base no w obtido, foi possível concluir seguindo o nosso modelo, que os principais fatores de risco para o AVC estão relacionados a hipertensão e ao tabagismo. Isso é bastante interessante e esperado, haja vista que é de conhecimento que esses são de fato causas comuns para o AVC, assim como é discutido no artigo "Investigação Etiológica do Acidente Vascular Cerebral no Adulto Jovem" e "Perfil epidemiológico dos idosos acometidos por acidente vascular cerebral".

Fontes Bibliográficas:
https://revista.spmi.pt/index.php/rpmi/article/view/482
https://dialnet.unirioja.es/servlet/articulo?codigo=6771953
