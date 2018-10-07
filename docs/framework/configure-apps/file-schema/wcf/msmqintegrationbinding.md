---
title: '&lt;msmqIntegrationBinding&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- msmqIntegrationBinding Element
ms.assetid: edf277f3-e3bf-4ed8-9f55-83b5788430a7
ms.openlocfilehash: 1493cb6f9588ee618b085186b3bb63476a9a8930
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841018"
---
# <a name="ltmsmqintegrationbindinggt"></a>&lt;msmqIntegrationBinding&gt;
Definisce un'associazione che fornisce supporto per l'accodamento mediante il routing dei messaggi tramite MSMQ.  
  
 \<system.ServiceModel>  
\<le associazioni >  
msmqIntegrationBinding  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<msmqIntegrationBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       customDeadLetterQueue="Uri"  
       deadLetterQueue="Uri"  
       durable="Boolean"  
       exactlyOnce="Boolean"   
       maxReceivedMessageSize"Integer"  
       maxRetryCycles="Integer"   
       name="string"   
       openTimeout="TimeSpan"        receiveContextEnabled="Boolean"  
       receiveErrorHandling="Drop/Fault/Move/Reject"  
       receiveTimeout="TimeSpan"   
       receiveRetryCount="Integer"  
       retryCycleDelay="TimeSpan"    
       sendTimeout="TimeSpan"   
       serializationFormat="XML/Binary/ActiveX/ByteArray/Stream">  
       timeToLive="TimeSpan"    
       useMsmqTracing="Boolean  
       useSourceJournal="Boolean"  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|closeTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|customDeadLetterQueue|URI che contiene il percorso della coda dei messaggi non recapitabili per applicazione, in cui vengono collocati i messaggi scaduti o che non possono essere trasferiti o recapitati.<br /><br /> La coda dei messaggi non recapitabili è una coda del gestore delle code dell'applicazione di origine contenente i messaggi scaduti che sono risultati non recapitabili.<br /><br /> L'URI specificato da <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> deve usare lo schema net.msmq.|  
|deadLetterQueue|Valore <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> che specifica quale tipo di coda dei messaggi non recapitabili usare, se presente.<br /><br /> Una coda dei messaggi non recapitabili è un oggetto in cui vengono trasferiti i messaggi che sono stati recapitati.<br /><br /> Per i messaggi che richiedono la garanzia exactlyOnce (ovvero per i messaggi per cui occorre che l'attributo `exactlyOnce` sia impostato su `true`), questo attributo viene impostato come valore predefinito su una coda dei messaggi non recapitabili transazionale a livello di sistema in MSMQ.<br /><br /> Per i messaggi che non richiedono alcuna garanzia, l'impostazione predefinita dell'attributo è `null`.|  
|durable|Valore booleano che indica se il messaggio nella coda è durevole o volatile. Un messaggio durevole sopravvive a un arresto del gestore delle code, un messaggio volatile no. I messaggi volatili sono utili quando le applicazioni richiedono minore latenza e possono tollerare messaggi perduti occasionalmente. Se l'attributo `exactlyOnce` è impostato su `true`, i messaggi devono essere durevoli. Il valore predefinito è `true`.|  
|exactlyOnce|Valore booleano che indica se ogni messaggio viene recapitato una sola volta. Il mittente riceverà quindi una notifica degli errori di recapito. Quando `durable` è `false`, questo attributo viene ignorato e i messaggi vengono trasferiti senza garanzia di recapito. Il valore predefinito è `true`. Per altre informazioni, vedere <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.|  
|maxReceivedMessageSize|Numero intero positivo che definisce la dimensione massima del messaggio, in byte, comprese le intestazioni, elaborate da questa associazione. Il mittente di un messaggio che supera questo limite riceverà un errore SOAP. Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia. Il valore predefinito è 65536. Questo vincolo alla dimensione dei messaggi limita l'esposizione agli attacchi di tipo Denial of Service (DoS).|  
|maxRetryCycles|Numero intero che indica il numero di cicli di ripetizione usati dalla funzionalità di rilevazione dei messaggi non elaborabili. Un messaggio diventa non elaborabile quando falliscono tutti i tentativi di recapito di tutti i cicli. Il valore predefinito è 2. Per altre informazioni, vedere <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.|  
|name|Stringa che contiene il nome della configurazione dell'associazione. Questo valore deve essere univoco perché viene usato per identificare l'associazione. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|receiveErrorHandling|Valore <xref:System.ServiceModel.ReceiveErrorHandling> che specifica come vengono gestiti i messaggi non elaborabili e non distribuibili.|  
|receiveRetryCount|Numero intero che specifica il numero massimo di tentativi immediati che Gestione code deve tentare se la trasmissione di un messaggio dalla coda dell'applicazione all'applicazione non riesce.<br /><br /> Se viene raggiunto il numero massimo di tentativi di recapito senza che l'applicazione acceda al messaggio, il messaggio viene inviato a una coda di tentativi per essere inviato nuovamente in seguito. Il periodo di tempo prima che il messaggio venga trasferito di nuovo alla coda di invio è controllato dall'elemento `retryCycleDelay`. Se i cicli di ripetizione raggiungono il valore `maxRetryCycles`, il messaggio viene inviato alla coda dei messaggi non elaborabili oppure viene inviato al mittente un messaggio di non riconoscimento.|  
|receiveTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:10:00.|  
|receiveContextEnabled|Valore booleano che specifica se il contesto di ricezione per l'elaborazione di messaggi nelle code è abilitato. Quando è impostato su `true`, un servizio può "leggere" un messaggio nella coda per avviarne l'elaborazione e, se si verifica un errore e viene generata un'eccezione, il messaggio rimane in coda. Servizi anche possono "bloccare" i messaggi per ritentare l'elaborazione in un secondo momento nel tempo. ReceiveContext offre un meccanismo per il "completamento" del messaggio al termine dell'elaborazione in modo che può essere rimosso dalla coda. Non sono più messaggi vengano letti e riscritti per le code sulla rete e i singoli messaggi non saranno rimbalzati tra diverse istanze del servizio durante l'elaborazione.|  
|retryCycleDelay|Valore TimeSpan che specifica l'intervallo di tempo tra i cicli di ripetizione dei tentativi di recapitare un messaggio che è impossibile recapitare immediatamente. Il valore definisce solo il tempo di attesa minimo, poiché è possibile che l'attesa effettiva sia più lunga. L'impostazione predefinita è 00:30:00. Per altre informazioni, vedere <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.|  
|sendTimeout|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|serializationFormat|Definisce il formato usato per la serializzazione del corpo del messaggio. L'attributo è di tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat>.|  
|timeToLive|Un valore TimeSpan che specifica la durata di validità dei messaggi prima che scadano e vengano inseriti nella coda dei messaggi non recapitabili. L'impostazione predefinita è 1.00:00:00.<br /><br /> L'attributo è impostato per verificare che i messaggi a scadenza non risultino non aggiornati prima di essere elaborati dalle applicazioni riceventi. Un messaggio in una coda che non viene usato dall'applicazione ricevente entro l'intervallo di tempo specificato viene considerato scaduto. I messaggi scaduti vengono inviati a una coda speciale denominata coda dei messaggi non recapitabili. Il percorso della coda dei messaggi non recapitabili viene impostato con l'attributo `DeadLetterQueue` o sul valore appropriato predefinito, in base alle garanzie.|  
|useMsmqTracing|Valore booleano che specifica se i messaggi elaborati da questa associazione devono essere tracciati. Il valore predefinito è `false`. Quando la traccia è attivata, i messaggi di rapporto vengono creati e inviati alla coda dei rapporti ogni volta che il messaggio viene inviato o ricevuto da un computer in cui è installato il sistema di accodamento messaggi.|  
|useSourceJournal|Valore booleano che specifica se le copie dei messaggi elaborati da questa associazione devono essere archiviate nella coda journal di origine. Il valore predefinito è `false`.<br /><br /> Le applicazioni in coda che devono tenere un registro dei messaggi che hanno lasciato la coda in uscita del computer possono copiare i messaggi in una coda journal. Quando un messaggio lascia la coda in uscita e viene ricevuto un riconoscimento che il messaggio è stato ricevuto nel computer di destinazione, una copia del messaggio viene mantenuta nella coda journal del sistema del computer di invio.|  
  
## <a name="serializationformat-attribute"></a>Attributo {serializationFormat}  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|Xml|Formato XML|  
|Binario|Formato binario|  
|ActiveX|Formato ActiveX|  
|ByteArray|Serializza l'oggetto in una matrice di byte.|  
|Flusso|Il corpo viene formattato come un flusso.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-msmqintegrationbinding.md)|Definisce le impostazioni di sicurezza per l'associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<bindings>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Questo elemento contiene una raccolta di associazioni standard e personalizzate.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di associazione può essere usato per consentire alle applicazioni di Windows Communication Foundation (WCF) inviare e ricevere messaggi da applicazioni MSMQ esistenti che usano COM, API native MSMQ o i tipi definiti nel <xref:System.Messaging?displayProperty=nameWithType> dello spazio dei nomi è può usare questo elemento di configurazione per specificare metodi per indirizzare la coda, garanzie di trasferimento, se i messaggi devono essere archiviati in modo durevole e come i messaggi devono essere protetti e autenticati. Per altre informazioni, vedere [procedura: scambiare messaggi con endpoint WCF e le applicazioni di Accodamento messaggi](../../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md).  
  
## <a name="example"></a>Esempio  
  
```xml  
<configuration>  
<system.ServiceModel>  
    <bindings>  
       <msmqIntegrationBinding>  
           <binding   
                    closeTimeout="00:00:10"   
                    openTimeout="00:00:20"   
                    receiveTimeout="00:00:30"   
                    sendTimeout="00:00:40"   
                    deadLetterQueue="net.msmq://localhost/blah"   
                    durable="true"   
                    exactlyOnce="true"   
                    maxReceivedMessageSize="1000"   
                    maxImmediateRetries="11"   
                    maxRetryCycles="12"  
                    poisonMessageHandling="Disabled"   
                    rejectAfterLastRetry="false"   
                    retryCycleDelay="00:05:55"   
                    timeToLive="00:11:11"   
                    useSourceJournal="true"   
                    useMsmqTracing="true"   
                    serializationFormat="Binary">  
                    <security mode="None" />  
           </binding>  
       </msmqIntegrationBinding  
   </bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
 [\<binding>](../../../../../docs/framework/misc/binding.md)  
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)  
 [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Uso di associazioni per configurare servizi e client](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Code in WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
