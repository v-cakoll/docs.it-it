---
title: <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: a68b44d7-7799-43a3-9e63-f07c782810a6
ms.openlocfilehash: 7456c6373c64e07b73e15e7e2bb229dce4032121
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140743"
---
# \<netMsmqBinding>
Definisce un'associazione in coda adatta per la comunicazione fra computer.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netMsmqBinding>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<netMsmqBinding>
  <binding closeTimeout="TimeSpan"
           customDeadLetterQueue="Uri"
           deadLetterQueue="Uri"
           durable="Boolean"
           exactlyOnce="Boolean"
           maxBufferPoolSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetryCycles="Integer"
           name="String"
           openTimeout="TimeSpan"
           poisonMessageHandling="Disabled/EnabledIfSupported"
           queueTransferProtocol="Native/Srmp/SrmpSecure"
           receiveErrorHandling="Drop/Fault/Move/Reject"
           receiveTimeout="TimeSpan"
           receiveRetryCount="Integer"
           rejectAfterLastRetry="Boolean"
           retryCycleDelay="TimeSpan"
           sendTimeout="TimeSpan"
           timeToLive="TimeSpan"
           useActiveDirectory="Boolean"
           useMsmqTracing="Boolean"
           useSourceJournal="Boolean">
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/InfoCard" />
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`closeTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di chiusura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|`customDeadLetterQueue`|URI che contiene il percorso della coda dei messaggi non recapitabili per applicazione, in cui vengono collocati i messaggi scaduti o che non possono essere trasferiti o recapitati.<br /><br /> La coda dei messaggi non recapitabili è una coda del gestore delle code dell'applicazione di origine contenente i messaggi scaduti che sono risultati non recapitabili.<br /><br /> L'URI specificato da <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> deve usare lo schema net.msmq.|  
|`deadLetterQueue`|Valore <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> che specifica quale tipo di coda dei messaggi non recapitabili usare, se presente.<br /><br /> Una coda dei messaggi non recapitabili è una posizione nella quale vengono trasferiti i messaggi che sono stati recapitati.<br /><br /> Per i messaggi che richiedono la garanzia `exactlyOnce`, ovvero, che l'attributo `exactlyOnce` sia impostato su `true`, questo attributo viene impostato come valore predefinito su una coda dei messaggi non recapitabili transazionale a livello di sistema in MSMQ.<br /><br /> Per i messaggi che non richiedono alcuna garanzia, l'impostazione predefinita dell'attributo è `null`.|  
|`durable`|Valore booleano che indica se il messaggio nella coda è durevole o volatile. Un messaggio durevole sopravvive a un arresto del gestore delle code, un messaggio volatile no. I messaggi volatili sono utili quando le applicazioni richiedono minore latenza e possono tollerare messaggi perduti occasionalmente. Se l'attributo `exactlyOnce` è impostato su `true`, i messaggi devono essere durevoli. Il valore predefinito è `true`.|  
|`exactlyOnce`|Valore booleano che indica se ciascun messaggio elaborato da questa associazione viene recapitato una sola volta. Il mittente riceverà quindi una notifica degli errori di recapito. Quando `durable` è `false`, questo attributo viene ignorato e i messaggi vengono trasferiti senza garanzia di recapito. Il valore predefinito è `true`. Per altre informazioni, vedere <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.|  
|`maxBufferPoolSize`|Numero intero che specifica la dimensione del pool di buffer massima per questa associazione. Il valore predefinito è 8.|  
|`maxReceivedMessageSize`|Numero intero positivo che definisce la dimensione massima del messaggio, in byte, comprese le intestazioni, elaborate da questa associazione. Il mittente di un messaggio che supera questo limite riceverà un errore SOAP. Il destinatario elimina il messaggio e crea una voce dell'evento nel registro di traccia. Il valore predefinito è 65536. Questo vincolo alla dimensione dei messaggi limita l'esposizione agli attacchi di tipo Denial of Service (DoS).|  
|`maxRetryCycles`|Numero intero che indica il numero di cicli di ripetizione usati dalla funzionalità di rilevazione dei messaggi non elaborabili. Un messaggio diventa non elaborabile quando falliscono tutti i tentativi di recapito di tutti i cicli. Il valore predefinito è 3. Per altre informazioni, vedere <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.|  
|`name`|Attributo obbligatorio. Stringa che contiene il nome della configurazione dell'associazione. Questo valore deve essere univoco perché viene usato per identificare l'associazione. A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di apertura. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|`QueueTransferProtocol`|Valore <xref:System.ServiceModel.QueueTransferProtocol> valido che specifica il trasporto del canale di comunicazione in coda usato da questa associazione. MSMQ non supporta l'indirizzamento di Active Directory in caso di utilizzo di SOAP Reliable Messaging Protocol. Pertanto, è consigliabile non impostare questo attributo su `Srmp` o `Srmps` quando l' `useActiveDirectory` attributo è impostato su `true` .|  
|`receiveErrorHandling`|Valore <xref:System.ServiceModel.ReceiveErrorHandling> che specifica come vengono gestiti i messaggi non elaborabili e non distribuibili.|  
|`receiveRetryCount`|Numero intero che specifica il numero massimo di tentativi eseguiti dal gestore delle code per inviare un messaggio prima che questo venga trasferito alla coda di tentativi.|  
|`receiveTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di ricezione. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:10:00.|  
|`retryCycleDelay`|Valore TimeSpan che specifica l'intervallo di tempo tra i cicli di ripetizione dei tentativi di recapitare un messaggio che è impossibile recapitare immediatamente. Il valore definisce solo il tempo di attesa minimo, poiché è possibile che l'attesa effettiva sia più lunga. L'impostazione predefinita è 00:10:00. Per altre informazioni, vedere <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.|  
|`sendTimeout`|Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo fornito per il completamento di un'operazione di invio. Questo valore deve essere maggiore o uguale a <xref:System.TimeSpan.Zero>. L'impostazione predefinita è 00:01:00.|  
|`timeToLive`|Un valore TimeSpan che specifica la durata di validità dei messaggi prima che scadano e vengano inseriti nella coda dei messaggi non recapitabili. L'impostazione predefinita è 1.00:00:00.<br /><br /> L'attributo è impostato per verificare che i messaggi a scadenza non risultino non aggiornati prima di essere elaborati dalle applicazioni riceventi. Un messaggio in una coda che non viene usato dall'applicazione ricevente entro l'intervallo di tempo specificato viene considerato scaduto. I messaggi scaduti vengono inviati a una coda speciale denominata coda dei messaggi non recapitabili. Il percorso della coda dei messaggi non recapitabili viene impostato con l'attributo `DeadLetterQueue` o sul valore appropriato predefinito, in base alle garanzie.|  
|`usingActiveDirectory`|Valore booleano che specifica se convertire gli indirizzi delle code mediante Active Directory.<br /><br /> Gli indirizzi delle code MSMQ possono essere costituiti da nomi di percorso o da nomi di formato Direct. Con un nome di formato Direct, MSMQ risolve il nome del computer usando DNS, NetBIOS o IP. Con un nome di percorso, MSMQ risolve il nome del computer usando Active Directory.<br /><br /> Per impostazione predefinita, il trasporto in coda Windows Communication Foundation (WCF) converte l'URI di una coda di messaggi in un nome di formato diretto. L'impostazione della proprietà `UseActiveDirectory` su true consente a un'applicazione di specificare che il trasporto in coda deve risolvere il nome del computer usando Active Directory invece di DNS, NetBIOS o IP.|  
|`useMsmqTracing`|Valore booleano che specifica se i messaggi elaborati da questa associazione devono essere tracciati. Il valore predefinito è `false`. Quando la traccia è attivata, i messaggi di rapporto vengono creati e inviati alla coda dei rapporti ogni volta che il messaggio viene inviato o ricevuto da un computer in cui è installato il sistema di accodamento messaggi.|  
|`useSourceJournal`|Valore booleano che specifica se le copie dei messaggi elaborati da questa associazione devono essere archiviate nella coda journal di origine. Il valore predefinito è `false`.<br /><br /> Le applicazioni in coda che devono tenere un registro dei messaggi che hanno lasciato la coda in uscita del computer possono copiare i messaggi in una coda journal. Quando un messaggio lascia la coda in uscita e viene ricevuto un riconoscimento che il messaggio è stato ricevuto nel computer di destinazione, una copia del messaggio viene mantenuta nella coda journal del sistema del computer di invio.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<security>](security-of-netmsmqbinding.md)|Definisce le impostazioni di sicurezza per l'associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|Questo elemento contiene una raccolta di associazioni standard e personalizzate.|  
  
## <a name="remarks"></a>Commenti  
 L'associazione `netMsmqBinding` fornisce il supporto per la gestione tramite coda basata sul sistema di accodamento dei messaggi MSMQ come trasporto. Tale associazione fornisce inoltre il supporto per le applicazioni a regime di controllo libero, per l'isolamento degli errori, per la distribuzione ottimale dei carichi e per le operazioni disconnesse. Per una descrizione di queste funzionalità, vedere [code in WCF](../../../wcf/feature-details/queues-in-wcf.md).  
  
## <a name="example"></a>Esempio  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netMsmqBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 deadLetterQueue="net.msmq://localhost/blah"
                 durable="true"
                 exactlyOnce="true"
                 maxReceivedMessageSize="1000"
                 maxRetries="11"
                 maxRetryCycles="12"
                 poisonMessageHandling="Disabled"
                 rejectAfterLastRetry="false"
                 retryCycleDelay="00:05:55"
                 timeToLive="00:11:11"
                 sourceJournal="true"
                 useMsmqTracing="true"
                 useActiveDirectory="true">
          <security>
            <message clientCredentialType="Windows" />
          </security>
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement>
- [\<binding>](bindings.md)
- [Binding](../../../wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [Code in WCF](../../../wcf/feature-details/queues-in-wcf.md)
