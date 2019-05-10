---
title: 'Procedura: Recuperare metadati e implementare un servizio conforme'
ms.date: 03/30/2017
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
ms.openlocfilehash: 18711c5d6b4c504b6b4334a7198ff7543c711622
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643606"
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a>Procedura: Recuperare metadati e implementare un servizio conforme
Spesso i servizi non vengono progettati e implementati dalla stessa persona. Negli ambienti dove le applicazioni interoperative svolgono un ruolo importante, i contratti possono essere progettati o descritti in WSDL (Web Services Description Language) e uno sviluppatore deve implementare un servizio che sia conforme al contratto fornito. È anche possibile eseguire la migrazione di un servizio esistente per Windows Communication Foundation (WCF) ma mantiene il formato di trasmissione. I contratti duplex richiedono inoltre ai chiamanti di implementare anche un contratto di callback.  
  
 In questi casi, è necessario usare il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (o un strumento equivalente) per generare un'interfaccia del contratto di servizio in un linguaggio gestito che è possibile implementare per soddisfare i requisiti del contratto. In genere il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) viene usato per acquisire un contratto di servizio che viene usato con una channel factory o un tipo di client WCF e con un file di configurazione client che consente di impostare l'associazione corretta e l'indirizzo. Per usare il file di configurazione generato, è necessario modificarlo in un file di configurazione del servizio. Può inoltre essere necessario modificare il contratto di servizio.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>Per recuperare dati e implementare un servizio conforme  
  
1. Usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) a fronte dei file di metadati o un endpoint di metadati per generare un file di codice.  
  
2. Cercare la parte del file di codice di output che contiene l'interfaccia desiderata (nel caso siano presenti più interfacce) contrassegnata con l'attributo <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>. Esempio di codice seguente illustra le due interfacce generate da [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). La prima (`ISampleService`) è l'interfaccia del contratto di servizio che viene implementata per creare un servizio conforme. La seconda (`ISampleServiceChannel`) è un'interfaccia di supporto usata dal client che estende sia l'interfaccia del contratto di servizio che l'interfaccia <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> e che viene usata in un'applicazione client.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3. Se la descrizione WSDL non specifica un'azione di replica per tutte le operazioni, è possibile che la proprietà <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> dei contratti di operazione generati sia impostata sul carattere jolly (*). Rimuovere l'impostazione di questa proprietà. In caso contrario, quando vengono implementati i metadati del contratto di servizio, i metadati non possono essere esportati per tali operazioni.  
  
4. Implementare l'interfaccia in una classe e ospitare il servizio. Per un esempio, vedere [Procedura: Implementare un contratto di servizio](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), oppure vedere una semplice implementazione riportata di seguito nella sezione esempio.  
  
5. Nella configurazione del client di file che il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) che genera l'errore, modificare il [ \<client >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) sezione di configurazione per un [ \<services >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sezione di configurazione. Per un esempio di file di configurazione dell'applicazione client generato, vedere la sezione "Esempio" seguente.  
  
6. All'interno del [ \<services >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) configurazione sezione, creare un `name` attributo il [ \<services >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) sezione di configurazione per il servizio implementazione.  
  
7. Impostare l'attributo `name` del servizio sul nome di configurazione da assegnare all'implementazione del servizio.  
  
8. Aggiungere gli elementi della configurazione endpoint che usano il contratto di servizio implementato alla sezione di configurazione del servizio.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente mostra la maggior parte di un file di codice generato eseguendo il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in file di metadati.  
  
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
