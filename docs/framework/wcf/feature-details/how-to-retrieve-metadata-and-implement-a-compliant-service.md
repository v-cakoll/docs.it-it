---
title: 'Procedura: recuperare metadati e implementare un servizio conforme'
ms.date: 03/30/2017
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
ms.openlocfilehash: 0a13d504b1c7c38ec13fee58c36913a75119271b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184855"
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a>Procedura: recuperare metadati e implementare un servizio conforme
Spesso i servizi non vengono progettati e implementati dalla stessa persona. Negli ambienti dove le applicazioni interoperative svolgono un ruolo importante, i contratti possono essere progettati o descritti in WSDL (Web Services Description Language) e uno sviluppatore deve implementare un servizio che sia conforme al contratto fornito. È anche possibile eseguire la migrazione di un servizio esistente a Windows Communication Foundation (WCF) ma mantenere il formato wire. I contratti duplex richiedono inoltre ai chiamanti di implementare anche un contratto di callback.  
  
 In questi casi, è necessario utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (o uno strumento equivalente) per generare un'interfaccia del contratto di servizio in un linguaggio gestito che è possibile implementare per soddisfare i requisiti del contratto. In genere lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) viene utilizzato per acquisire un contratto di servizio utilizzato con una channel factory o un tipo di client WCF, nonché con un file di configurazione client che imposta l'associazione e l'indirizzo corretti. Per usare il file di configurazione generato, è necessario modificarlo in un file di configurazione del servizio. Può inoltre essere necessario modificare il contratto di servizio.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>Per recuperare dati e implementare un servizio conforme  
  
1. Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) su file di metadati o un endpoint di metadati per generare un file di codice.  
  
2. Cercare la parte del file di codice di output che contiene l'interfaccia desiderata (nel caso siano presenti più interfacce) contrassegnata con l'attributo <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>. Nell'esempio di codice riportato di seguito vengono illustrate le due interfacce generate dallo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). La prima (`ISampleService`) è l'interfaccia del contratto di servizio che viene implementata per creare un servizio conforme. La seconda (`ISampleServiceChannel`) è un'interfaccia di supporto usata dal client che estende sia l'interfaccia del contratto di servizio che l'interfaccia <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> e che viene usata in un'applicazione client.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3. Se la descrizione WSDL non specifica un'azione di replica per tutte le operazioni, è possibile che la proprietà <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> dei contratti di operazione generati sia impostata sul carattere jolly (*). Rimuovere l'impostazione di questa proprietà. In caso contrario, quando vengono implementati i metadati del contratto di servizio, i metadati non possono essere esportati per tali operazioni.  
  
4. Implementare l'interfaccia in una classe e ospitare il servizio. Per un esempio, vedere [Procedura: implementare un contratto](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)di servizio o vedere una semplice implementazione di seguito nella sezione Esempio.  
  
5. Nel file di configurazione client generato dallo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe),](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) modificare la [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) sezione di configurazione del client>in una [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sezione di configurazione>dei servizi. Per un esempio di file di configurazione dell'applicazione client generato, vedere la sezione "Esempio" seguente.  
  
6. All'interno della [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) `name` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sezione di configurazione dei>dei servizi, creare un attributo nella sezione di configurazione dei servizi>per l'implementazione del servizio.  
  
7. Impostare l'attributo `name` del servizio sul nome di configurazione da assegnare all'implementazione del servizio.  
  
8. Aggiungere gli elementi della configurazione endpoint che usano il contratto di servizio implementato alla sezione di configurazione del servizio.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrata la maggior parte di un file di codice generato eseguendo lo strumento [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) su file di metadati.  
  
 Il codice seguente include:  
  
- L'interfaccia del contratto di servizio che, quando implementata, è conforme ai requisiti del contratto (`ISampleService`).  
  
- L'interfaccia di supporto usata dal client che estende sia l'interfaccia del contratto di servizio che l'interfaccia <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> e che viene usata in un'applicazione client (`ISampleServiceChannel`).  
  
- La classe di supporto che estende <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> e che deve essere usata in un'applicazione client (`SampleServiceClient`).  
  
- Il file di configurazione generato dal servizio.  
  
- Una semplice implementazione del servizio `ISampleService`.  
  
- Una conversione del file di configurazione lato client in una versione lato servizio.  
  
[!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]

[!code-xml[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]

[!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]

[!code-xml[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]
  
## <a name="see-also"></a>Vedere anche

- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
