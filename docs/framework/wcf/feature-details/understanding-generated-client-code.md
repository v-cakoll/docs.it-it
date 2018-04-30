---
title: Informazioni sul codice client generato
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c3f6e4b0-1131-4c94-aa39-a197c5c2f2ca
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8cd3e7f5ac8f129e29ed080cbf510dfe106edfb7
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="understanding-generated-client-code"></a>Informazioni sul codice client generato
Lo [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) genera il codice client e un file di configurazione dell'applicazione client da usare per la compilazione di applicazioni client. In questo argomento viene fornita una panoramica degli esempi di codice generati per gli scenari del contratto di servizio standard. Per ulteriori informazioni sulla compilazione di un'applicazione client utilizzando il codice generato, vedere [panoramica dei Client WCF](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
## <a name="overview"></a>Panoramica  
 Se si utilizza Visual Studio per generare [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] tipi di client per il progetto, in genere non è necessaria esaminare il codice client generato. Se non si usa un ambiente di sviluppo che esegue automaticamente gli stessi servizi, è possibile usare uno strumento quale Svcutil.exe per generare codice client e usare tale codice per sviluppare l'applicazione client.  
  
 Poiché Svcutil.exe dispone di alcune opzioni che modificano le informazioni sui tipi generati, in questo argomento non verranno esaminati tutti gli scenari. Tuttavia, nelle attività standard seguenti è coinvolta l'individuazione del codice generato:  
  
-   Identificazione delle interfacce del contratto di servizio.  
  
-   Identificazione della classe client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
-   Identificazione dei tipi di dati.  
  
-   Identificazione di contratti di callback per i servizi duplex.  
  
-   Identificazione dell'interfaccia del contratto di servizio di assistenza.  
  
### <a name="finding-service-contract-interfaces"></a>Individuazione delle interfacce del contratto di servizio  
 Per individuare le interfacce che modellano i contratti di servizio, cercare le interfacce contrassegnate con l'attributo <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>. Spesso questo attributo può essere difficile da individuare con una lettura rapida a causa della presenza di altri attributi e di proprietà esplicite impostate sull'attributo stesso. Ricordare che l'interfaccia del contratto di servizio e l'interfaccia del contratto client sono due tipi diversi. Nell'esempio di codice seguente viene illustrato il contratto di servizio originale.  
  
 [!code-csharp[C_GeneratedCodeFiles#22](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#22)]  
  
 Nell'esempio di codice seguente viene illustrato lo stesso contratto di servizio generato da Svcutil.exe.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 È possibile usare l'interfaccia del contratto di servizio generata insieme alla classe <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> per creare un oggetto del canale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con il quale richiamare operazioni del servizio. Per altre informazioni, vedere [procedura: usare ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md).  
  
### <a name="finding-wcf-client-classes"></a>Ricerca della classi client WCF  
 Per identificare la classe client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che implementa il contratto di servizio da usare, ricercare un'estensione di <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>, in cui il parametro di tipo è l'interfaccia del contratto di servizio precedentemente individuata che estende l'interfaccia. Nell'esempio di codice seguente viene illustrata la classe <xref:System.ServiceModel.ClientBase%601> del tipo `ISampleService`.  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 È possibile usare questa classe client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] creandone una nuova istanza e chiamando i metodi che implementa. Tali metodi richiamano l'operazione del servizio con la quale è progettato e configurato per interagire. Per altre informazioni, vedere [panoramica dei Client WCF](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
> [!NOTE]
>  Quando SvcUtil.exe genera una classe client WCF, aggiunge <xref:System.Diagnostics.DebuggerStepThroughAttribute> alla classe client che impedisce ai debugger di eseguire la classe client WCF un'istruzione alla volta.  
  
### <a name="finding-data-types"></a>Ricerca dei tipi di dati  
 Per individuare i tipi di dati nel codice generato, il meccanismo più basilare consiste nell'identificare il nome del tipo specificato in un contratto e cercare tale dichiarazione del tipo nel codice. Ad esempio, il contratto seguente specifica che `SampleMethod` può restituire un errore SOAP di tipo `microsoft.wcf.documentation.SampleFault`.  
  
 [!code-csharp[C_GeneratedCodeFiles#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#11)]  
  
 Se si esegue una ricerca per `SampleFault` , viene individuata la dichiarazione di tipo seguente.  
  
 [!code-csharp[C_GeneratedCodeFiles#30](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#30)]  
  
 In questo caso il tipo di dati è il tipo di dettaglio generato da un'eccezione specifica sul client, una <xref:System.ServiceModel.FaultException%601> in cui il parametro di tipo del dettaglio è `microsoft.wcf.documentation.SampleFault`. Per ulteriori informazioni sui tipi di dati, vedere [che specifica di trasferimento dei dati nei contratti di servizio](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md). Per ulteriori informazioni sulla gestione delle eccezioni nei client, vedere [invio e ricezione di errori](../../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
### <a name="finding-callback-contracts-for-duplex-services"></a>Individuazione dei contratti di callback per i servizi duplex  
 Se si individua un contratto di servizio per il quale l'interfaccia del contratto specifica un valore per la proprietà <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>, quel contratto specifica un contratto duplex. I contratti duplex richiedono che l'applicazione client crei una classe di callback che implementa il contratto di callback e passa un'istanza di quella classe all'oggetto <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType> o <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType> usato per comunicare con il servizio. Per ulteriori informazioni sui client duplex, vedere [procedura: servizi di accesso con un contratto Duplex](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).  
  
 Nel contratto seguente viene specificato un contratto di callback di tipo `SampleDuplexHelloCallback`.  
  
 [!code-csharp[C_GeneratedCodeFiles#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/duplexproxycode.cs#2)]
 [!code-vb[C_GeneratedCodeFiles#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_generatedcodefiles/vb/duplexproxycode.vb#2)]  
  
 Se si esegue una ricerca per tale contratto di callback, viene identificata l'interfaccia seguente che l'applicazione client deve implementare.  
  
 [!code-csharp[C_GeneratedCodeFiles#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/duplexproxycode.cs#4)]
 [!code-vb[C_GeneratedCodeFiles#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_generatedcodefiles/vb/duplexproxycode.vb#4)]  
  
### <a name="finding-service-contract-channel-interfaces"></a>Individuazione delle interfacce del canale del contratto di servizio  
 Quando si usa la classe <xref:System.ServiceModel.ChannelFactory> con un'interfaccia del contratto del servizio, per aprire, chiudere o interrompere in modo esplicito il canale è necessario eseguire il cast all'interfaccia <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>. Per semplificare l'uso, lo strumento Svcutil.exe genera inoltre un'interfaccia di supporto che implementa l'interfaccia del contratto del servizio e <xref:System.ServiceModel.IClientChannel> per consentire l'interazione con l'infrastruttura del canale client senza dovere eseguire il cast. Nel codice seguente viene illustrata la definizione di un canale client di supporto che implementa il contratto del servizio precedente.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica dei client WCF](../../../../docs/framework/wcf/wcf-client-overview.md)
