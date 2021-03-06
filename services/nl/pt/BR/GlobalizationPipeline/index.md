---

copyright:
  years: 2015, 2016

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}


# Introdução do
{{site.data.keyword.GlobalizationPipeline_full}}
{: #globalizationpipeline}

*Última atualização: 6 de julho de 2016*
{: .last-updated}

{{site.data.keyword.GlobalizationPipeline_full}} é um serviço que fornece tradução de máquina e recursos de edição para traduzir rapidamente IUs da web ou móveis. Com seu painel, API RESTful e integração com o pipeline de entrega de seu app, é possível liberar para clientes globais sem ter de reconstruir ou reimplementar seu app.
{:shortdesc}

É possível usar o serviço {{site.data.keyword.GlobalizationPipeline_full}} com qualquer app no {{site.data.keyword.Bluemix}}, ou desvinculado, sozinho. É possível criar, manter e revisar traduções rapidamente, com esforço mínimo e sem precisar sair de seu ambiente DevOps.

Na interface do {{site.data.keyword.GlobalizationPipeline_full}}, é possível traduzir rapidamente seus apps {{site.data.keyword.Bluemix_notm}}. Para obter informações sobre como traduzir seus apps usando a API RESTful, consulte [Referência de API](https://gp-rest.ng.bluemix.net/translate/swagger/index.html){: new_window}. 


## Criando um pacote configurável
{: #globalizationpipeline_creatingbundles}

Com o serviço {{site.data.keyword.GlobalizationPipeline_full}}, é possível
criar pacotes configuráveis, que incluem os arquivos de recursos de seus apps que serão
traduzidos. Os arquivos de recursos podem ser de propriedades Java, AMD I18N ou JSON e
devem ter conteúdo na forma de pares de chave/valor que representem as sequências da IU
do seu app. Para obter mais detalhes e exemplos de tipos de arquivos suportados, consulte
[Trabalhando com pacotes configuráveis](./bundles.html){: new_window}.

Para criar um pacote configurável, conclua as etapas a seguir:

1\. Na guia **Visão geral**, clique em **Novo pacote configurável**.

2\. Forneça as informações sobre o pacote configurável:

| Campo | Obrigatória| Descri‡Æo|
|-------|---------|------------|
| **ID do pacote
** | Sim | Um nome exclusivo para identificar o pacote configurável. |
| **Idioma de origem
** | Sim | O idioma nativo do arquivo de origem. |
| **Arquivo de Recursos** | NÃO | Um [arquivo de recursos](bundles.html#globalizationpipeline_workingwithbundles) a ser traduzido. O tamanho máximo do arquivo é limitado a 2MB. Os arquivos de recursos especificados serão transferidos por upload.  |
| **Formato de arquivo ** | NÃO | O tipo de arquivo que está sendo transferido por upload. |
| **Idioma de destino** | NÃO | Os idiomas para os quais você deseja traduções. |

**Nota:** para mudar o serviço de idioma que fornece tradução de máquina para seus pacotes configuráveis, clique na guia [**Configuração de MT**](./managing_translations.html#globalizationpipeline_service_to_service) para visualizar outros mecanismos de tradução de máquina suportados.

3\. Clique em**Salvar**

Após o pacote configurável ser criado, o arquivo de recursos transferido por
upload é traduzido em todos os idiomas de destino especificados. O novo pacote
configurável é incluído na guia Pacotes configuráveis, na qual é possível:

* Incluir ou remover idiomas
* Editar as traduções geradas
* Atualizar o arquivo de origem usado no pacote configurável e gerar novamente as traduções

## Importando pacotes configuráveis traduzidos para o serviço
{: #globalizationpipeline_importtranslatedbundlesintoservice}

Como alternativa, se você já tiver arquivos de recursos traduzidos, será possível importá-los para o novo pacote configurável. Para obter mais informações, consulte [Ferramentas do cliente Java para o {{site.data.keyword.GlobalizationPipeline_full}}](https://github.com/IBM-Bluemix/gp-java-tools).

**Nota:** se o arquivo de origem original for atualizado, as chaves e valores definidos no arquivo serão sincronizados com a versão mais recente do arquivo de origem para que somente as chaves e valores mudados sejam traduzidos.

## Estimando o uso de dados do {{site.data.keyword.GlobalizationPipeline_full}}
{: #globalizationpipeline_documentpricing}

O {{site.data.keyword.GlobalizationPipeline_full}} armazena suas traduções em um banco de dados de backend. Para estimar o tamanho de dados ativos, é possível consultar a fórmula a seguir:

`<tamanho esperado do armazenamento de dados de recurso em MB> ˜= 0.0005 * <número de pares de chave/valor no recurso de origem> * <número de idiomas incluindo o idioma de origem>`

De acordo com a fórmula, o tamanho de um pacote configurável típico é `(comprimento da chave + comprimento do valor em UTF-8 = ˜40 bytes)`.

Por exemplo, se você tiver 100 pares de chave/valor e traduzi-los para 9 idiomas, o tamanho estimado do armazenamento será 0.0005 100 (9+1) = 0.5 MB. O tamanho real poderá ser diferente dependendo do tamanho real da chave/valor e dos metadados armazenados com a tradução.

Use a
[calculadora
de precificação](https://console.ng.bluemix.net/?direct=classic/#/pricing/cloudOEPaneId=pricing&paneId=pricingSheet&orgGuid=127a45f4-4461-4d5b-a26b-6dc2fdd1a3a2&spaceGuid=208fb1ff-413b-4fd9-9615-e8226062d0f3) do Bluemix para determinar seus custos mensais do serviço.


# Links Relacionados
{: #rellinks}
## Tutoriais e amostras
{: #samples}

* [Amostra do Node.js](https://github.com/IBM-Bluemix/gp-nodejs-sample){: new_window}
* [Amostra do Ruby](https://github.com/IBM-Bluemix/gp-ruby-sample){: new_window}

## SDK
{: #sdk}

* [Java Client](https://github.com/IBM-Bluemix/gp-java-client){: new_window}
* [Java Tools](https://github.com/IBM-Bluemix/gp-java-tools){: new_window}
* [JavaScript Client](https://github.com/IBM-Bluemix/gp-js-client){: new_window}
* [AngularJS Client](https://github.com/IBM-Bluemix/gp-angular-client){: new_window}
* [Ruby Client](https://github.com/IBM-Bluemix/gp-ruby-client){: new_window}
* [Python Client](https://github.com/IBM-Bluemix/gp-python-client){: new_window}

## Referência de API
{: #api}

* [API RESTful do IBM Globalization Pipeline](https://gp-rest.ng.bluemix.net/translate/swagger/index.html){: new_window}

## Links Relacionados
{: #general}

* [Integrar o Globalization Pipeline com o pipeline de entrega](https://hub.jazz.net/docs/deploy_ext/#globalize){: new_window}
* [Folha de precificação do IBM Bluemix](https://www.ng.bluemix.net/#/pricing){: new_window}
* [Pré-requisitos do IBM Bluemix](https://developer.ibm.com/bluemix/support/#prereqs){: new_window}
