---
title: 'Procedura: importare informazioni WSDL personalizzate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 00a845fe5c8321d521fb7baa3b16bd009fc3e660
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="e607c-102">Procedura: importare informazioni WSDL personalizzate</span><span class="sxs-lookup"><span data-stu-id="e607c-102">How to: Import Custom WSDL</span></span>
<span data-ttu-id="e607c-103">In questo argomento viene descritto come importare informazioni WSDL personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e607c-103">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="e607c-104">Per gestire le informazioni WSDL personalizzate, è necessario implementare l'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="e607c-104">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="e607c-105">Per importare informazioni WSDL personalizzate</span><span class="sxs-lookup"><span data-stu-id="e607c-105">To import custom WSDL</span></span>  
  
1.  <span data-ttu-id="e607c-106">Implementare <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="e607c-106">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="e607c-107">Implementare il metodo <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> per modificare i metadati prima che siano importati.</span><span class="sxs-lookup"><span data-stu-id="e607c-107">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="e607c-108">Implementare i metodi <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> e <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> per modificare i contratti e gli endpoint importati dai metadati.</span><span class="sxs-lookup"><span data-stu-id="e607c-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="e607c-109">Per accedere al contratto o all'endpoint personalizzato, usare l'oggetto contesto corrispondente (<xref:System.ServiceModel.Description.WsdlContractConversionContext> o <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span><span class="sxs-lookup"><span data-stu-id="e607c-109">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
    ```  
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
  
2.  <span data-ttu-id="e607c-110">Configurare l'applicazione client per l'uso dell'unità di importazione WSDL personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e607c-110">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="e607c-111">Si noti che se si sta usando Svcutil.exe, è necessario aggiungere questa configurazione al file di configurazione di Svcutil.exe (Svcutil.exe.config):</span><span class="sxs-lookup"><span data-stu-id="e607c-111">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
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
  
3.  <span data-ttu-id="e607c-112">Creare una nuova istanza di <xref:System.ServiceModel.Description.WsdlImporter> (passando l'istanza di <xref:System.ServiceModel.Description.MetadataSet> che contiene i documenti WSDL che si desidera importare) e chiamare <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span><span class="sxs-lookup"><span data-stu-id="e607c-112">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);          System.Collections.ObjectModel.Collection<ContractDescription> contracts  = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e607c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e607c-113">See Also</span></span>  
 [<span data-ttu-id="e607c-114">Metadati</span><span class="sxs-lookup"><span data-stu-id="e607c-114">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="e607c-115">Esportazione e importazione di metadati</span><span class="sxs-lookup"><span data-stu-id="e607c-115">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)  
 [<span data-ttu-id="e607c-116">Pubblicazione WSDL personalizzata</span><span class="sxs-lookup"><span data-stu-id="e607c-116">Custom WSDL Publication</span></span>](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)
