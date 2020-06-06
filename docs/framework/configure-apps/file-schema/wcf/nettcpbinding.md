---
title: <netTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: c43c141093c8287adb6d5a841a43ac893deefccd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139335"
---
# \<netTcpBinding>

Specifica un'associazione protetta, affidabile e ottimizzata adatta per le comunicazioni fra computer. Per impostazione predefinita, genera uno stack di comunicazione in fase di runtime con Windows per la sicurezza per garantire la sicurezza e l'autenticazione dei messaggi, TCP per il recapito dei messaggi e la codifica binaria dei messaggi.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<netTcpBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="None/Transport/Message/Both">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
      <transport clientCredentialType="None/Windows/Certificate"
                 protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`closeTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|`hostNameComparisonMode`|Specifica la modalità di confronto del nome host HTTP usata per analizzare gli URI. L'attributo è di tipo <xref:System.ServiceModel.HostNameComparisonMode>, che indica se il nome host viene usato per raggiungere il servizio in caso di corrispondenza nell'URI. Il valore predefinito è <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, che ignora il nome host nella corrispondenza.|  
|`listenBacklog`|Numero intero positivo che specifica il numero massimo di canali di attesa accettati nel listener. Le connessioni in eccesso vengono messe in coda finché il numero di connessioni non risulta inferiore al limite consentito. L'attributo `connectionTimeout` limita il tempo di attesa della connessione da parte del client prima che venga generata un'eccezione. Il valore predefinito è 10.|  
|`maxBufferPoolSize`|Numero intero che specifica la dimensione del pool di buffer massima per questa associazione. Il valore predefinito è 512 * 1024 byte. Molte parti di Windows Communication Foundation (WCF) usano buffer. La creazione e l'eliminazione definitiva dei buffer a ogni uso sono operazioni onerose, analogamente a quelle di Garbage Collection dei buffer. Quando si usa un pool di buffer è possibile prelevare un buffer dal pool, usarlo e, al termine delle operazioni, riporlo nel pool. In questo modo è possibile evitare il sovraccarico dovuto alla creazione e all'eliminazione definitiva dei buffer.|  
|`maxBufferSize`|Numero intero positivo che specifica la dimensione massima, in byte, del buffer usato per archiviare messaggi in memoria.<br /><br /> Se l'attributo `transferMode` è uguale a `Buffered`, questo attributo deve essere uguale al valore dell'attributo `maxReceivedMessageSize`.<br /><br /> Se l'attributo `transferMode` è uguale a `Streamed`, questo attributo non può essere superiore al valore dell'attributo `maxReceivedMessageSize` e deve essere uguale almeno alla dimensione delle intestazioni.<br /><br /> Il valore predefinito è 65536. Per altre informazioni, vedere <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.|  
|`maxConnections`|Numero intero che specifica il numero massimo di connessioni in uscita e in ingresso che il servizio creerà e accetterà. Le connessioni in ingresso e in uscita vengono conteggiate in base a un limite distinto specificato da questo attributo.<br /><br /> Le connessioni in ingresso eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.<br /><br /> Le connessioni in uscita eccedenti il limite vengono messe in coda finché non è disponibile uno spazio inferiore al limite.<br /><br /> Il valore predefinito è 10.|  
|`maxReceivedMessageSize`|Integer positivo che specifica la dimensione massima del messaggio, incluse le intestazioni, che è possibile ricevere su un canale configurato con questa associazione. Il mittente di un messaggio che supera questo limite riceverà un errore SOAP. Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia. Il valore predefinito è 65536.|  
|`name`|Stringa che contiene il nome della configurazione dell'associazione. Questo valore deve essere univoco perché viene usato per identificare l'associazione. A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|`portSharingEnabled`|Valore booleano che specifica se è attivata la condivisione delle porte TCP per la connessione. Se è `false`, ciascuna associazione usa la propria porta esclusiva. Questa impostazione è appropriata solo per i servizi in quanto non ha effetto per i client.|  
|`receiveTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:10:00.|  
|`sendTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|`transactionFlow`|Valore booleano che specifica se l'associazione supporta la propagazione di WS-Transactions. Il valore predefinito è `false`.|  
|`transactionProtocol`|Specifica il protocollo di transazione da usare con questa associazione. I valori validi sono:<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> L'impostazione predefinita è OleTransactions. L'attributo è di tipo <xref:System.ServiceModel.TransactionProtocol>.|  
|`transferMode`|Valore <xref:System.ServiceModel.TransferMode> che specifica se i messaggi vengono memorizzati nel buffer o inviati nel flusso o sono una richiesta o una risposta.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|Definisce le impostazioni di sicurezza per l'associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Specifica se vengono stabilite sessioni affidabili tra endpoint del canale.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|Questo elemento contiene una raccolta di associazioni standard e personalizzate.|  
  
## <a name="remarks"></a>Commenti

Per impostazione predefinita, questa associazione genera uno stack di comunicazione runtime che, oltre a implementare la codifica binaria dei messaggi, usa la sicurezza del trasporto e il protocollo TCP per il recapito dei messaggi. Questa associazione è una scelta fornita dal sistema Windows Communication Foundation (WCF) appropriata per la comunicazione su una rete Intranet.  
  
 La configurazione predefinita per `netTcpBinding` è più veloce rispetto alla configurazione fornita da `wsHttpBinding` , ma è destinata solo alla comunicazione WCF. Il comportamento di sicurezza può essere configurato usando l'attributo `securityMode` facoltativo. L'utilizzo del protocollo WS-ReliableMessaging può essere configurato usando l'attributo facoltativo `reliableSessionEnabled`. La messaggistica affidabile è tuttavia disattivata per impostazione predefinita. Più in generale, le associazioni HTTP fornite dal sistema, ad esempio `wsHttpBinding` e `basicHttpBinding`, sono configurate in modo da attivare modalità di supporto per impostazione predefinita, mentre l'associazione `netTcpBinding` le disattiva per impostazione predefinita e pertanto è necessario fornire un consenso esplicito per ottenere il supporto, ad esempio, per una delle specifiche WS-*. Ciò significa che la configurazione predefinita per le associazioni TCP è più veloce nello scambio dei messaggi tra endpoint rispetto a quelle predefinite per le associazioni HTTP.  
  
## <a name="example"></a>Esempio

L'associazione è specificata nei file di configurazione per il client e il servizio. Il tipo di associazione è specificato nell'attributo `binding` dell'elemento `<endpoint>`. Se si desidera configurare l'associazione netTcpBinding e modificare alcune delle relative impostazioni, è necessario definire una configurazione di associazione. L'endpoint deve fare riferimento alla configurazione di associazione con un attributo `bindingConfiguration`. Nell'esempio seguente viene modificata una configurazione di associazione.  
  
```xml  
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
    <endpoint address=""
              binding="netTcpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
    ...
  </service>
</services>
<bindings>
  <netTcpBinding>
    <binding closeTimeout="00:01:00"
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"
                       enabled="false" />
      <security mode="Transport">
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />
      </security>
    </binding>
  </netTcpBinding>
</bindings>
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [Binding](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
