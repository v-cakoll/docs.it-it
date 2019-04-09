---
title: "Procedura: Scrivere un'estensione per ServiceContractGenerator"
ms.date: 03/30/2017
ms.assetid: 876ca823-bd16-4bdf-9e0f-02092df90e51
ms.openlocfilehash: 104f65f76429701dbf02c1c7a5d737e50b080394
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111592"
---
# <a name="how-to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="897ec-102">Procedura: Scrivere un'estensione per ServiceContractGenerator</span><span class="sxs-lookup"><span data-stu-id="897ec-102">How to: Write an Extension for the ServiceContractGenerator</span></span>
<span data-ttu-id="897ec-103">In questo argomento viene illustrato come scrivere un'estensione per la classe <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span><span class="sxs-lookup"><span data-stu-id="897ec-103">This topic describes how to write an extension for the <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span></span> <span data-ttu-id="897ec-104">A tal fine è necessario implementare l'interfaccia <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> su un comportamento di operazione oppure l'interfaccia <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> su un comportamento di contratto.</span><span class="sxs-lookup"><span data-stu-id="897ec-104">This can be done by implementing the <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> interface on an operation behavior or implementing the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span> <span data-ttu-id="897ec-105">In questo argomento viene illustrato come implementare l'interfaccia <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> in un comportamento di contratto.</span><span class="sxs-lookup"><span data-stu-id="897ec-105">This topic shows how to implement the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span>  
  
 <span data-ttu-id="897ec-106"><xref:System.ServiceModel.Description.ServiceContractGenerator> genera contratti di servizio, tipi di client e configurazioni client da istanze <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> e <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="897ec-106">The <xref:System.ServiceModel.Description.ServiceContractGenerator> generates service contracts, client types, and client configurations from <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances.</span></span> <span data-ttu-id="897ec-107">In genere, si importano istanze <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> e <xref:System.ServiceModel.Channels.Binding> da metadati del servizio e si utilizzano quindi tali istanze per generare il codice necessario per chiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="897ec-107">Typically, you import <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances from service metadata and then use these instances to generate code to call the service.</span></span> <span data-ttu-id="897ec-108">In questo esempio viene utilizzata un'implementazione <xref:System.ServiceModel.Description.IWsdlImportExtension> per elaborare annotazioni WSDL e aggiungere estensioni di generazione del codice ai contratti importati al fine di generare commenti sul codice generato.</span><span class="sxs-lookup"><span data-stu-id="897ec-108">In this example, an <xref:System.ServiceModel.Description.IWsdlImportExtension> implementation is used to process WSDL annotations and then add code generation extensions to the imported contracts to generate comments on the generated code.</span></span>  
  
### <a name="to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="897ec-109">Scrivere un'estensione per ServiceContractGenerator</span><span class="sxs-lookup"><span data-stu-id="897ec-109">To write an extension for the ServiceContractGenerator</span></span>  
  
1.  <span data-ttu-id="897ec-110">Implementare <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span><span class="sxs-lookup"><span data-stu-id="897ec-110">Implement <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="897ec-111">Per modificare il contratto di servizio generato, utilizzare l'istanza <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passata nel metodo <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>.</span><span class="sxs-lookup"><span data-stu-id="897ec-111">To modify the generated service contract, use the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> instance passed into the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> method.</span></span>  
  
    ```  
    public void GenerateContract(ServiceContractGenerationContext context)  
    {  
        Console.WriteLine("In generate contract.");  
    context.ContractType.Comments.AddRange(Formatter.FormatComments(commentText));  
    }  
    ```  
  
2.  <span data-ttu-id="897ec-112">Implementare <xref:System.ServiceModel.Description.IWsdlImportExtension> nella stessa classe.</span><span class="sxs-lookup"><span data-stu-id="897ec-112">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension> on the same class.</span></span> <span data-ttu-id="897ec-113">Il metodo <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> consente di elaborare un'estensione WSDL specifica (annotazioni WSDL in questo caso) mediante l'aggiunta di un'estensione di generazione del codice all'istanza <xref:System.ServiceModel.Description.ContractDescription> importata.</span><span class="sxs-lookup"><span data-stu-id="897ec-113">The <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> method can process a specific WSDL extension (WSDL annotations in this case) by adding a code generation extension to the imported <xref:System.ServiceModel.Description.ContractDescription> instance.</span></span>  
  
    ```  
    public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
       {  
                // Contract documentation  
             if (context.WsdlPortType.Documentation != null)  
             {  
                    context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
             }  
             // Operation documentation  
             foreach (Operation operation in context.WsdlPortType.Operations)  
             {  
                if (operation.Documentation != null)  
                {  
                   OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
                   if (operationDescription != null)  
                   {  
                            operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
                   }  
                }  
             }  
          }  
          public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)   
            {  
                Console.WriteLine("BeforeImport called.");  
            }  
  
          public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)   
            {  
                Console.WriteLine("ImportEndpoint called.");  
            }  
    ```  
  
3.  <span data-ttu-id="897ec-114">Aggiungere l'unità di importazione WSDL alla configurazione del client.</span><span class="sxs-lookup"><span data-stu-id="897ec-114">Add the WSDL importer to your client configuration.</span></span>  
  
    ```xml  
    <metadata>  
      <wsdlImporters>  
        <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
      </wsdlImporters>  
    </metadata>  
    ```  
  
4.  <span data-ttu-id="897ec-115">Nel codice client creare `MetadataExchangeClient` e chiamare `GetMetadata`.</span><span class="sxs-lookup"><span data-stu-id="897ec-115">In the client code, create a `MetadataExchangeClient` and call `GetMetadata`.</span></span>  
  
    ```  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(metadataAddress);  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet metaDocs = mexClient.GetMetadata();  
    ```  
  
5.  <span data-ttu-id="897ec-116">Creare un `WsdlImporter` e chiamare `ImportAllContracts`.</span><span class="sxs-lookup"><span data-stu-id="897ec-116">Create a `WsdlImporter` and call `ImportAllContracts`.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);            System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
6.  <span data-ttu-id="897ec-117">Creare `ServiceContractGenerator` e chiamare `GenerateServiceContractType` per ogni contratto.</span><span class="sxs-lookup"><span data-stu-id="897ec-117">Create a `ServiceContractGenerator` and call `GenerateServiceContractType` for each contract.</span></span>  
  
    ```  
    ServiceContractGenerator generator = new ServiceContractGenerator();  
    foreach (ContractDescription contract in contracts)  
    {  
       generator.GenerateServiceContractType(contract);  
    }  
    if (generator.Errors.Count != 0)  
       throw new Exception("There were errors during code compilation.");  
    ```  
  
7.  <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> <span data-ttu-id="897ec-118">viene chiamato automaticamente per ogni comportamento del contratto in un determinato contratto che implementa <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span><span class="sxs-lookup"><span data-stu-id="897ec-118">is called automatically for each contract behavior on a given contract that implements <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="897ec-119">Questo metodo può quindi modificare l'oggetto <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passato.</span><span class="sxs-lookup"><span data-stu-id="897ec-119">This method can then modify the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passed in.</span></span> <span data-ttu-id="897ec-120">In questo esempio vengono aggiunti commenti.</span><span class="sxs-lookup"><span data-stu-id="897ec-120">In this example comments are added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="897ec-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="897ec-121">See also</span></span>

- [<span data-ttu-id="897ec-122">Metadati</span><span class="sxs-lookup"><span data-stu-id="897ec-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="897ec-123">Procedura: Importare informazioni WSDL personalizzate</span><span class="sxs-lookup"><span data-stu-id="897ec-123">How to: Import Custom WSDL</span></span>](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)
