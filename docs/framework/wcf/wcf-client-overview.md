---
title: Panoramica dei client WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7434e0ea112a6641e356a1ec3da3a4bd6524bdda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="wcf-client-overview"></a>Panoramica dei client WCF
Contenuto della sezione vengono descritte le operazioni svolte delle applicazioni client e vengono fornite istruzioni su come configurare, creare e usare un client [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], nonché su come proteggere le applicazioni client.  
  
## <a name="using-wcf-client-objects"></a>Uso di oggetti client WCF  
 Un'applicazione client è un'applicazione gestita che usa un client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per comunicare con un'altra applicazione. Per creare un'applicazione client per un servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è necessario eseguire i passaggi seguenti:  
  
1.  Ottenere le informazioni relative al contratto di servizio, alle associazioni e all'indirizzo per un endpoint di servizio.  
  
2.  Creare un client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] usando queste informazioni.  
  
3.  Chiamare le operazioni.  
  
4.  Chiudere l'oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Nelle sezioni seguenti vengono illustrate queste procedure e vengono fornite informazioni introduttive sugli argomenti seguenti:  
  
-   Gestione degli errori.  
  
-   Configurazione e protezione dei client.  
  
-   Creazione di oggetti di callback per i servizi duplex.  
  
-   Chiamate ai servizi in modo asincrono.  
  
-   Chiamate ai servizi mediante canali client.  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>Ottenere informazioni sul contratto di servizio, sulle associazioni e sugli indirizzi  
 In [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servizi e client modellano i contratti usando attributi, interfacce e metodi gestiti. Per eseguire la connessione a un servizio in un'applicazione client è necessario ottenere le informazioni sul tipo per il contratto di servizio. In genere, si farlo tramite il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), che consente di scaricare i metadati dal servizio, viene convertito in un file di codice sorgente gestito nel linguaggio di propria scelta e crea un client file di configurazione dell'applicazione che è possibile utilizzare per configurare il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] oggetto client. Ad esempio, se si intende creare un oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per richiamare un servizio `MyCalculatorService` e i metadati per questo servizio sono pubblicati in `http://computerName/MyCalculatorService/Service.svc?wsdl`, l'esempio di codice seguente mostra come usare Svcutil.exe per ottenere un file `ClientCode.vb` che contenga il contratto di servizio nel codice gestito.  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 È possibile compilare questo codice di contratto nell'applicazione client o in un altro assembly che l'applicazione client potrà successivamente usare per creare un oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Per configurare l'oggetto client per eseguire la connessione al servizio in modo appropriato, è possibile usare il file di configurazione.  
  
 Per un esempio di questo processo, vedere [procedura: creare un Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Per ulteriori informazioni sui contratti, vedere [contratti](../../../docs/framework/wcf/feature-details/contracts.md).  
  
## <a name="create-a-wcf-client-object"></a>Creare un oggetto client WCF  
 Un client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] è un oggetto locale che rappresenta un servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] in una forma che il client può usare per comunicare con il servizio remoto. I tipi di client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] implementano il contratto di servizio di destinazione, pertanto quando se ne crea e configura uno, è possibile usare direttamente l'oggetto client per richiamare le operazioni del servizio. Il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] converte ora il metodo chiama in messaggi, li invia al servizio, resta in attesa di replica e restituisce questi valori per eseguire il [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] oggetto client come valori restituiti o `out` o `ref` parametri.  
  
 Per eseguire la connessione ai servizi e usarli è anche possibile usare oggetti del canale client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Per informazioni dettagliate, vedere [architettura Client WCF](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
#### <a name="creating-a-new-wcf-object"></a>Creazione di un nuovo oggetto WCF  
 Per illustrare l'uso di una classe <xref:System.ServiceModel.ClientBase%601>, si supponga che il contratto di servizio seguente sia stato generato da un'applicazione di servizio.  
  
> [!NOTE]
>  Se per creare il client [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] si usa [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], quando al progetto viene aggiunto un riferimento a servizi gli oggetti vengono caricati automaticamente nel Visualizzatore oggetti.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Se non si usa [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], esaminare il codice del contratto generato per individuare il tipo che estende la classe <xref:System.ServiceModel.ClientBase%601> e l'interfaccia del contratto di servizio `ISampleService`. In questo caso il tipo ha l'aspetto del codice seguente:  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 Questa classe può essere creata come un oggetto locale usando uno dei costruttori, configurata e quindi usata per la connessione a un servizio del tipo `ISampleService`.  
  
 È consigliabile creare prima l'oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], quindi usare e chiudere questo oggetto in un singolo blocco Try/Catch. Non usare l'istruzione `using` (`Using` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) in quanto potrebbe mascherare eccezioni in determinate modalità di errore. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]le sezioni seguenti anche come [evitare problemi con l'istruzione Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
### <a name="contracts-bindings-and-addresses"></a>Contratti, associazioni e indirizzi.  
 Per poter creare un oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], è necessario configurare prima l'oggetto client. In particolare, deve avere un servizio *endpoint* da utilizzare. Un endpoint è la combinazione di un contratto di servizio, un'associazione e un indirizzo. ([!INCLUDE[crabout](../../../includes/crabout-md.md)] endpoint, vedere [endpoint: indirizzi, associazioni e contratti](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) In genere, queste informazioni si trovano nel [ \<endpoint >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) elemento in un file di configurazione dell'applicazione client, ad esempio quello dello strumento Svcutil.exe genera l'errore e viene caricato automaticamente quando si crea il client oggetto. Entrambi i tipi di client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] dispongono inoltre di overload che consentono di specificare queste informazioni a livello di programmazione.  
  
 Ad esempio, un file di configurazione generato per un servizio `ISampleService` usato negli esempi precedenti contiene le informazioni sull'endpoint riportate di seguito.  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 Questo file di configurazione specifica un endpoint di destinazione nell'elemento `<client>`. [!INCLUDE[crabout](../../../includes/crabout-md.md)]ll'utilizzo di più endpoint di destinazione, vedere i costruttori <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType>.  
  
## <a name="calling-operations"></a>Chiamate alle operazioni  
 Dopo avere creato e configurato un oggetto client, creare un blocco Try/Catch, chiamare le operazioni nello stesso modo in cui verrebbero chiamate nel caso di un oggetto locale, quindi chiudere l'oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Quando l'applicazione client chiama la prima operazione, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] apre automaticamente il canale sottostante e quest'ultimo viene chiuso quando l'oggetto viene riciclato. In alternativa, è possibile aprire e chiudere il canale in modo esplicito prima o dopo la chiamata ad altre operazioni.  
  
 Si supponga, ad esempio, di disporre del contratto di servizio seguente:  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
   {  
        [OperationContract]  
        double Add(double n1, double n2);  
        [OperationContract]  
        double Subtract(double n1, double n2);  
        [OperationContract]  
        double Multiply(double n1, double n2);  
        [OperationContract]  
        double Divide(double n1, double n2);  
    }  
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _   
   Public Interface ICalculator  
        <OperationContract> _   
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 È possibile chiamare operazioni creando un oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] e chiamando i relativi metodi, come illustrato nell'esempio di codice seguente. L'apertura, la chiamata e la chiusura dell'oggetto client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] si verificano all'interno di un singolo blocco Try/Catch. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][L'accesso ai servizi tramite Client WCF](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) e [evitare problemi con l'istruzione Using](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>Gestione degli errori  
 In un'applicazione client possono verificarsi eccezioni quando si apre il canale client sottostante (sia in modo esplicito che automaticamente chiamando un'operazione), quando si usa l'oggetto client o l'oggetto canale per chiamare operazioni o quando si chiude il canale client sottostante. Oltre a gestire qualsiasi oggetto <xref:System.TimeoutException?displayProperty=nameWithType> generato come risultato di errori SOAP restituiti dalle operazioni, le applicazioni dovrebbero essere configurate per gestire almeno possibili eccezioni <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> e <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>. Gli errori SOAP specificati nel contratto dell'operazione vengono generati nelle applicazioni client come oggetto <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> dove il parametro di tipo è il tipo di dettaglio dell'errore SOAP. [!INCLUDE[crabout](../../../includes/crabout-md.md)]la gestione delle condizioni di errore in un'applicazione client, vedere [invio e ricezione di errori](../../../docs/framework/wcf/sending-and-receiving-faults.md). Per un esempio completo che mostra come gestire gli errori in un client, vedere [previsto eccezioni](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
## <a name="configuring-and-securing-clients"></a>Configurazione e protezione dei client  
 La configurazione di un client inizia con il caricamento obbligatorio di informazioni sull'endpoint di destinazione per il client o per l'oggetto del canale, generalmente da un file di configurazione, sebbene sia possibile caricare queste informazioni anche a livello di programmazione usando i costruttori e le proprietà del client. Per attivare determinati comportamenti del client e per numerosi scenari di sicurezza sono tuttavia necessarie operazioni di configurazione aggiuntive.  
  
 I requisiti di sicurezza per i contratti di servizio, ad esempio, vengono dichiarati nell'interfaccia del contratto di servizio e se lo strumento Svcutil.exe ha creato un file di configurazione, questo file contiene in genere un'associazione in grado di supportare i requisiti di sicurezza del servizio. In alcuni casi può essere però necessaria un'ulteriore configurazione della protezione, ad esempio la configurazione di credenziali client. Per informazioni complete sulla configurazione di sicurezza per [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, vedere [protezione di client](../../../docs/framework/wcf/securing-clients.md).  
  
 Nelle applicazioni client possono essere inoltre abilitate alcune modifiche personalizzate, ad esempio comportamenti personalizzati nella fase di esecuzione. [!INCLUDE[crabout](../../../includes/crabout-md.md)]come configurare un comportamento client personalizzato, vedere [configurazione dei comportamenti Client](../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
## <a name="creating-callback-objects-for-duplex-services"></a>Creazione di oggetti di callback per i servizi duplex  
 I servizi duplex specificano un contratto di callback che l'applicazione client deve implementare per fornire un oggetto di callback affinché il servizio esegua la chiamata in base ai requisiti del contratto. Sebbene gli oggetti di callback non siano servizi completi (ad esempio, non è possibile avviare un canale con un oggetto di callback), ai fini dell'implementazione e della configurazione possono essere considerati come una specie di servizio.  
  
 I client di servizi duplex devono:  
  
-   Implementare una classe di contratto di callback.  
  
-   Creare un'istanza della classe di implementazione del contratto di callback e usarla per creare l'oggetto <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> che viene passato al costruttore client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
-   Richiamare operazioni e gestire callback di operazioni.  
  
 Gli oggetti client duplex di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] funzionano come le relative controparti non duplex, tranne per il fatto che espongono la funzionalità necessaria per supportare i callback, inclusa la configurazione del servizio di callback.  
  
 È possibile controllare, ad esempio, i vari aspetti del comportamento degli oggetti di callback in fase di esecuzione usando proprietà dell'attributo <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> nella classe di callback. Un altro esempio è l'uso della classe <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> per attivare la restituzione di informazioni sull'eccezione ai servizi che chiamano l'oggetto di callback. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Servizi duplex](../../../docs/framework/wcf/feature-details/duplex-services.md). Per un esempio completo, vedere [Duplex](../../../docs/framework/wcf/samples/duplex.md).  
  
 Nei computer Windows XP che eseguono Internet Information Services (IIS) 5.1, i client duplex devono specificare un indirizzo client di base usando la classe <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>. In caso contrario verrà generata un'eccezione. Nel codice di esempio seguente viene illustrato come eseguire questa procedura nel codice.  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 Il codice seguente mostra come eseguire la procedura in un file di configurazione.  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>Chiamate ai servizi in modo asincrono  
 La modalità in cui vengono chiamate le operazioni dipende interamente dallo sviluppatore client. Ciò è dovuto al fatto che i messaggi che costituiscono un'operazione possono essere mappati a metodi sincroni o asincroni quando vengono espressi in codice gestito. Pertanto, se si desidera compilare un client che chiama operazioni in modo asincrono, è possibile usare Svcutil.exe per generare codice client asincrono usando l'opzione `/async`. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Procedura: chiamare operazioni del servizio in modo asincrono](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).  
  
## <a name="calling-services-using-wcf-client-channels"></a>Chiamate ai servizi mediante canali client di WCF  
 I tipi di client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] estendono la classe <xref:System.ServiceModel.ClientBase%601>, che deriva essa stessa dall'interfaccia <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> per esporre il sistema di canali sottostante. È possibile richiamare servizi usando il contratto di servizio di destinazione con la classe <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Per informazioni dettagliate, vedere [architettura Client WCF](../../../docs/framework/wcf/feature-details/client-architecture.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
