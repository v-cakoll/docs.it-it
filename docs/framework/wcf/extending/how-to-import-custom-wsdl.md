---
title: 'Procedura: importare informazioni WSDL personalizzate'
ms.date: 03/30/2017
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
ms.openlocfilehash: 614842f2d77d967e0a6d4841e5e5e4fcc8805580
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185554"
---
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="b89b8-102">Procedura: importare informazioni WSDL personalizzate</span><span class="sxs-lookup"><span data-stu-id="b89b8-102">How to: Import Custom WSDL</span></span>
<span data-ttu-id="b89b8-103">In questo argomento viene descritto come importare informazioni WSDL personalizzate.</span><span class="sxs-lookup"><span data-stu-id="b89b8-103">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="b89b8-104">Per gestire le informazioni WSDL personalizzate, è necessario implementare l'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="b89b8-104">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="b89b8-105">Per importare informazioni WSDL personalizzate</span><span class="sxs-lookup"><span data-stu-id="b89b8-105">To import custom WSDL</span></span>  
  
1. <span data-ttu-id="b89b8-106">Implementare <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="b89b8-106">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="b89b8-107">Implementare il metodo <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> per modificare i metadati prima che siano importati.</span><span class="sxs-lookup"><span data-stu-id="b89b8-107">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="b89b8-108">Implementare i metodi <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> e <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> per modificare i contratti e gli endpoint importati dai metadati.</span><span class="sxs-lookup"><span data-stu-id="b89b8-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="b89b8-109">Per accedere al contratto o all'endpoint personalizzato, usare l'oggetto contesto corrispondente (<xref:System.ServiceModel.Description.WsdlContractConversionContext> o <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span><span class="sxs-lookup"><span data-stu-id="b89b8-109">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
    ```csharp
    public class WsdlDocumentationImporter : IWsdlImportExtension
    {
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
    }
    ```
  
2. <span data-ttu-id="b89b8-110">Configurare l'applicazione client per l'uso dell'unità di importazione WSDL personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b89b8-110">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="b89b8-111">Si noti che se si sta usando Svcutil.exe, è necessario aggiungere questa configurazione al file di configurazione di Svcutil.exe (Svcutil.exe.config):</span><span class="sxs-lookup"><span data-stu-id="b89b8-111">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint
              address="http://localhost:8000/Fibonacci"
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3. <span data-ttu-id="b89b8-112">Creare una nuova istanza di <xref:System.ServiceModel.Description.WsdlImporter> (passando l'istanza di <xref:System.ServiceModel.Description.MetadataSet> che contiene i documenti WSDL che si desidera importare) e chiamare <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span><span class="sxs-lookup"><span data-stu-id="b89b8-112">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b89b8-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b89b8-113">See also</span></span>

- [<span data-ttu-id="b89b8-114">Metadati</span><span class="sxs-lookup"><span data-stu-id="b89b8-114">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="b89b8-115">Esportazione e importazione di metadati</span><span class="sxs-lookup"><span data-stu-id="b89b8-115">Exporting and Importing Metadata</span></span>](../feature-details/exporting-and-importing-metadata.md)
- [<span data-ttu-id="b89b8-116">Pubblicazione WSDL personalizzata</span><span class="sxs-lookup"><span data-stu-id="b89b8-116">Custom WSDL Publication</span></span>](../samples/custom-wsdl-publication.md)
