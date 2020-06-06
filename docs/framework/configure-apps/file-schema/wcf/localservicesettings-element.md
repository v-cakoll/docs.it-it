---
title: Elemento <localServiceSettings>
ms.date: 03/30/2017
ms.assetid: 0658549c-3f65-46dd-8c5c-9895441ed734
ms.openlocfilehash: 4883fd563ecf989d67c369085df4fc43d0c5f078
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400308"
---
# <a name="localservicesettings-element"></a>Elemento \<localServiceSettings>
Specifica le impostazioni di sicurezza di un servizio locale per questa associazione.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localServiceSettings>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<security>
  <localServiceSettings detectReplays="Boolean"
                        inactivityTimeout="TimeSpan"
                        issuedCookieLifeTime="TimeSpan"
                        maxCachedCookies="Integer"
                        maxClockSkew="TimeSpan"
                        maxPendingSessions="Integer"
                        maxStatefulNegotiations="Integer"
                        negotiationTimeout="TimeSpan"
                        reconnectTransportOnFailure="Boolean"
                        replayCacheSize="Integer"
                        replayWindow="TimeSpan"
                        sessionKeyRenewalInterval="TimeSpan"
                        sessionKeyRolloverInterval="TimeSpan"
                        timestampValidityDuration="TimeSpan" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`detectReplays`|Valore booleano che specifica se gli attacchi di tipo replay contro il canale vengono rilevati e gestiti automaticamente. Il valore predefinito è `false`.|  
|`inactivityTimeout`|Valore positivo <xref:System.TimeSpan> che specifica la durata dell'inattività del canale prima del timeout. Il valore predefinito è "01:00:00".|  
|`issuedCookieLifeTime`|<xref:System.TimeSpan> specifica la durata di tutti i nuovi cookie di sicurezza. I cookie che superano la durata vengono riciclati e devono essere negoziati di nuovo. Il valore predefinito è "10:00:00".|  
|`maxCachedCookies`|Un numero intero positivo che specifica il numero massimo di cookie che possono essere memorizzati nella cache. Il valore predefinito è 1000.|  
|`maxClockSkew`|<xref:System.TimeSpan> specifica la differenza massima di tempo tra gli orologi di sistema delle due parti che stanno comunicando. Il valore predefinito è "00:05:00".<br /><br /> Quando l'impostazione di questo valore è quella predefinita, il destinatario accetta i messaggi con timestamp relativi all'ora di invio precedenti o successivi all'ora in cui il messaggio è stato ricevuto. I messaggi che non passano i test dell'ora di invio vengono rifiutati. Questa impostazione viene usata in combinazione con l'attributo `replayWindow`.|  
|`maxPendingSessions`|Un numero intero positivo che specifica il numero massimo di sessioni di sicurezza in sospeso supportate dal servizio. Quando questo limite viene raggiunto, tutti i nuovi client ricevono errori SOAP. Il valore predefinito è 1000.|  
|`maxStatefulNegotiations`|Un numero intero positivo che specifica il numero massimo di negoziazioni di sicurezza che possono essere attive contemporaneamente. Le sessioni di negoziazione che superano il limite vengono messe in coda e possono essere completate solo quando diventa disponibile uno spazio inferiore al limite. Il valore predefinito è 1024.|  
|`negotiationTimeout`|Un valore <xref:System.TimeSpan> che specifica la durata del criterio di sicurezza usato dal canale. Quando il periodo scade, il canale negozia un nuovo criterio di sicurezza con il client. Il valore predefinito è "00:02:00".|  
|`reconnectTransportOnFailure`|Valore booleano che specifica se le connessioni che usano WS-Reliable Messaging tenteranno la riconnessione in caso di errori del trasporto. L'impostazione predefinita è `true`, la quale significa un numero infinito di tentativi di riconnessione. Il ciclo viene interrotto dal timeout di inattività che fa sì che il canale generi un'eccezione quando la riconnessione non è possibile.|  
|`replayCacheSize`|Un numero intero positivo che specifica il numero di parametri nonce da usare per il rilevamento di attacchi di tipo replay. Se questo limite viene superato, il nonce meno recente viene rimosso e viene creato un nuovo nonce per il messaggio nuovo. Il valore predefinito è 500000.|  
|`replayWindow`|<xref:System.TimeSpan> specifica la durata di validità dei singoli nonce dei messaggi.<br /><br /> Dopo questa durata, un messaggio inviato con lo stesso nonce di quello inviato precedentemente non verrà accettato. Questo attributo viene usato in combinazione con l'attributo `maxClockSkew` per impedire attacchi di tipo replay. L'autore di un attacco può replicare un messaggio dopo che la finestra di replay è scaduta. Questo messaggio, tuttavia, non supererebbe il test `maxClockSkew` che rifiuta i messaggi con timestamp relativi all'ora di invio che differiscono di un tempo specificato in più o in meno rispetto all'ora in cui il messaggio è stato ricevuto.|  
|`sessionKeyRenewalInterval`|<xref:System.TimeSpan> specifica l'intervallo di tempo dopo il quale l'iniziatore rinnoverà la chiave per la sessione di sicurezza. L'impostazione predefinita è "10:00:00".|  
|`sessionKeyRolloverInterval`|<xref:System.TimeSpan> specifica l'intervallo di tempo per il quale la chiave della sessione precedente è valida nei messaggi in arrivo durante un rinnovo della chiave. L'impostazione predefinita è "00:05:00".<br /><br /> Durante il rinnovo della chiave, client e server devono inviare i messaggi usando sempre la chiave disponibile più recente. Entrambe le parti accetteranno i messaggi in arrivo protetti con la chiave della sessione precedente fino alla scadenza del tempo di sostituzione.|  
|`timestampValidityDuration`|<xref:System.TimeSpan> positivo che specifica il periodo di validità di un timestamp. L'impostazione predefinita è "00:15:00".|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|Specifica le opzioni di sicurezza di un'associazione personalizzata.|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|Specifica i valori predefiniti usati per iniziare un servizio di conversazione protetta.|  
  
## <a name="remarks"></a>Commenti  
 Le impostazioni sono locali perché non vengono pubblicate unitamente ai criteri di sicurezza del servizio e non influiscono sull'associazione del client.  
  
 Gli attributi seguenti dell'elemento `localServiceSecuritySettings` consentono di attenuare un attacco di tipo Denial of Service (DoS):  
  
- `maxCachedCookies`: controlla il numero massimo di token SecurityContextTokens temporali memorizzati dal server nella cache dopo la negoziazione SPNEGO o SSL.  
  
- `issuedCookieLifetime`: controlla la durata dei token SecurityContextTokens emessi dal server in seguito alla negoziazione SPNEGO o SSL. Il server memorizza nella cache il token SecurityContextTokens per questo periodo di tempo.  
  
- `maxPendingSessions`: controlla il numero massimo di conversazioni protette stabilite nel server, per cui però non sono stati elaborati messaggi dell'applicazione. Questa quota impedisce ai client di stabilire conversazioni protette nel servizio, facendo così in modo che il servizio mantenga lo stato per ogni client, senza mai usare i client.  
  
- `inactivityTimeout`: controlla il periodo di tempo massimo in cui il servizio mantiene attiva una conversazione protetta senza mai ricevere un messaggio di un'applicazione. Questa quota impedisce ai client di stabilire conversazioni protette nel servizio, facendo così in modo che il servizio mantenga lo stato per ogni client, senza mai usare i client.  
  
 In una sessione di conversazione protetta, entrambi gli attributi `inactivityTimeout` e `receiveTimeout` nell'associazione influiscono sul timeout della sessione. Il valore inferiore tra i due determina quando si verificano i timeout.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Binding](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Sicurezza delle associazioni personalizzate](../../../wcf/samples/custom-binding-security.md)
