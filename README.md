# Code Guideline
## _Boas práticas, dicas e explicações_

Esta página servirá como um guia para nomenclaturas, dicas de boas práticas e algumas convenções. Nada aqui está _escrito em pedra_ e poderá ser rediscutido ou complementado sempre que novas ideias ou sugestões forem surgindo. Além disso, este arquivo é apenas um guia e não precisará ser _levado ao pé da letra_. 
Como um bom engenheiro de software, use sua criatividade e bom senso para criar mas sempre pensando que outro engenheiro irá ler seu código.

## Organização de arquivos

##### Evite pacotes granulares
Observe:
| O que não fazer ❌ | O que fazer ✅ |
| ----- | ----- |
|![O que não fazer](https://user-images.githubusercontent.com/22798147/212448971-0563645b-f298-4d7e-b7ea-fc207d06ebde.png) | ![O que fazer](https://user-images.githubusercontent.com/22798147/212449012-e20f39d5-b7f2-4e79-86eb-1ac805cdbe16.png) |

> A granularidade fará com que pacotes sejam criados para muitas vezes armazenar pouquíssimos arquivos. Isso deixará a visualização menos compacta, quando no segundo exemplo é possível bater o olho e encontrar o arquivo desejado. Mas para isso, é importante nomear bem os arquivos.

##### Entidades e seus mappers

Pensando em desacoplar camadas, principalmente de frameworks utilizados (Appolo, REST, etc.), pensamos da seguinte maneira

![Fluxo arquitetural](https://user-images.githubusercontent.com/22798147/212449938-eac28030-60e0-47b7-923d-2d196be9d422.png)

**Motivação:**
Por estarmos lidando com um framework que atualiza e remove informações de forma "automática", asseguramos quebra de informações ao traduzir dados advindos do framework em nossas informações, validando cada variável através de mappers e, reforçando, evitando efeitos colaterais indesejados da atualização automática do framework.

Com isso, surgiu a dúvida de onde devemos colocar os mappers e qual tradução cada camada de mapper deve ter. Chegamos a seguinte conclusão:

![Fluxo de Mappers](https://user-images.githubusercontent.com/22798147/212450626-8b9dced8-364a-4cf8-ae55-cc08e0d67555.png)

Levando em conta que `data` é modular e `view object` baseado em funcionalidades (cada _feature_ terá seu próprio pacote de `view object` enquanto `data` será único para o módulo), ficamos com a seguinte visualização:

![Data Mappers](https://user-images.githubusercontent.com/22798147/212449012-e20f39d5-b7f2-4e79-86eb-1ac805cdbe16.png)
![View Objects Mappers](https://user-images.githubusercontent.com/22798147/212452083-27d760f5-7869-4483-8995-2a76a530ff84.png)

##### Disposição de arquivos e pastas (arquitetural)

É comum questionarmos onde deve ficar determinado arquivo ou classe. Veja a disposição sugerida:

![Disposição em camadas](https://user-images.githubusercontent.com/22798147/212457431-dc1caa7f-a96c-47d6-bab8-f9ff00ea7916.png)

Seguimos ela. Com isso, temos uma demonstração da disposição:

<img width="275" alt="Disposição em arquivos" src="https://user-images.githubusercontent.com/22798147/212457454-f18703c5-b267-4d0e-9a9e-7418a9ec65dd.png">
