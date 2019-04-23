---
title: Propagazione
ms.date: 03/30/2017
ms.assetid: f8181e75-d693-48d1-b333-a776ad3b382a
ms.openlocfilehash: faa0e6ecb53963587e3fc253cd8beae1dc2c4bf5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154037"
---
# <a name="propagation"></a>Propagazione
In questo argomento viene descritta la propagazione di attività nel modello di traccia di Windows Communication Foundation (WCF).  
  
## <a name="using-propagation-to-correlate-activities-across-endpoints"></a>Utilizzo della propagazione per correlare attività attraverso endpoint  
 La propagazione fornisce all'utente la correlazione diretta delle tracce di errore per la stessa unità di elaborazione attraverso endpoint dell'applicazione, ad esempio, una richiesta. Gli errori generati in endpoint diversi per la stessa unità di elaborazione vengono raggruppati nella stessa attività, anche attraverso domini applicazione. Questa operazione viene eseguita tramite la propagazione dell'ID attività nelle intestazioni del messaggio. Se, pertanto, un client va in timeout a causa di un errore interno nel server, entrambi gli errori vengono visualizzati nella stessa attività per la correlazione diretta.  
  
 A tale scopo, usare l'impostazione `ActivityTracing` come illustrato nell'esempio precedente. Impostare inoltre l'attributo `propagateActivity` per l'origine di traccia `System.ServiceModel` in tutti gli endpoint.  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing" propagateActivity="true" >  
```  
  
 Propagazione di attività è una funzionalità configurabile che fa sì che WCF aggiungere un'intestazione ai messaggi in uscita, che include l'ID attività in TLS. Includendo questa intestazione nelle tracce successive lato server, è possibile correlare le attività di client e server.  
  
## <a name="propagation-definition"></a>Definizione di propagazione  
 Il gAId dell'attività M viene propagato all'attività N se si applicano tutte le condizioni seguenti.  
  
-   N viene creato a causa di M  
  
-   Il gAId di M è conosciuto a N  
  
-   Il gAId di N è uguale al gAId di M.  
  
 Il gAId viene propagato tramite l'intestazione del messaggio ActivityId, come illustrato nell'XML Schema seguente.  
  
```xml  
<xsd:element name="ActivityId" type="integer" minOccurs="0">  
  <xsd:attribute name="CorrelationId" type="integer" minOccurs="0"/>  
</xsd:element>  
```  
  
 Di seguito è riportato un esempio di intestazione del messaggio.  
  
```xml  
<MessageLogTraceRecord>  
  <s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope"
                      xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      <a:Action s:mustUnderstand="1">http://Microsoft.ServiceModel.Samples/ICalculator/Subtract  
      </a:Action>  
      <a:MessageID>urn:uuid:f0091eae-d339-4c7e-9408-ece34602f1ce  
      </a:MessageID>  
      <ActivityId CorrelationId="f94c6af1-7d5d-4295-b693-4670a8a0ce34"
               xmlns="http://schemas.microsoft.com/2004/09/ServiceModel/Diagnostics">  
        17f59a29-b435-4a15-bf7b-642ffc40eac8  
      </ActivityId>  
      <a:ReplyTo>  
          <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
      </a:ReplyTo>  
      <a:To s:mustUnderstand="1">net.tcp://localhost/servicemodelsamples/service</a:To>  
   </s:Header>  
   <s:Body>  
     <Subtract xmlns="http://Microsoft.ServiceModel.Samples">  
       <n1>145</n1>  
       <n2>76.54</n2>  
     </Subtract>  
   </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
```  
  
## <a name="propagation-and-activity-boundaries"></a>Limiti della propagazione e dell'attività  
 Quando l'ID attività viene propagato attraverso endpoint, il destinatario del messaggio emette tracce Start e Stop con quell'ID attività (propagato). Esiste pertanto una traccia Start e Stop con quel gAId da ogni origine di traccia. Se gli endpoint sono nello stesso processo e usano lo stesso nome di origine di traccia, vengono creati più Start e Stop con lo stesso lAId (stesso gAId, stessa origine di traccia, stesso processo).  
  
## <a name="synchronization"></a>Sincronizzazione  
 Per sincronizzare eventi attraverso endpoint che vengono eseguiti in computer diversi, viene aggiunto un CorrelationId all'intestazione ActivityId propagata nei messaggi. Gli strumenti possono usare questo ID per sincronizzare gli eventi attraverso computer con discrepanza dell'orologio. Nello specifico, lo strumento Visualizzatore delle tracce dei servizi usa questo ID per visualizzare i flussi dei messaggi tra endpoint.  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione delle funzionalità di traccia](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [Uso del visualizzatore di tracce dei servizi per la visualizzazione di tracce correlate e la risoluzione dei problemi](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Scenari di traccia end-to-end](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [Strumento Visualizzatore di tracce dei servizi (SvcTraceViewer.exe)](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
