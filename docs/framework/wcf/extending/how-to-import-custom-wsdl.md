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
# <a name="how-to-import-custom-wsdl"></a>Procedura: importare informazioni WSDL personalizzate
In questo argomento viene descritto come importare informazioni WSDL personalizzate. Per gestire le informazioni WSDL personalizzate, è necessario implementare l'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension>.  
  
### <a name="to-import-custom-wsdl"></a>Per importare informazioni WSDL personalizzate  
  
1. Implementare <xref:System.ServiceModel.Description.IWsdlImportExtension>. Implementare il metodo <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> per modificare i metadati prima che siano importati. Implementare i metodi <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> e <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> per modificare i contratti e gli endpoint importati dai metadati. Per accedere al contratto o all'endpoint personalizzato, usare l'oggetto contesto corrispondente (<xref:System.ServiceModel.Description.WsdlContractConversionContext> o <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):  
  
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
  
2. Configurare l'applicazione client per l'uso dell'unità di importazione WSDL personalizzata. Si noti che se si sta usando Svcutil.exe, è necessario aggiungere questa configurazione al file di configurazione di Svcutil.exe (Svcutil.exe.config):  
  
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
  
3. Creare una nuova istanza di <xref:System.ServiceModel.Description.WsdlImporter> (passando l'istanza di <xref:System.ServiceModel.Description.MetadataSet> che contiene i documenti WSDL che si desidera importare) e chiamare <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Metadati](../feature-details/metadata.md)
- [Esportazione e importazione di metadati](../feature-details/exporting-and-importing-metadata.md)
- [Pubblicazione WSDL personalizzata](../samples/custom-wsdl-publication.md)
