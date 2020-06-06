---
title: Elemento <localClientSettings>
ms.date: 03/30/2017
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
ms.openlocfilehash: 3ec0394943c030a8866087c98a912682a2a2112e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400314"
---
# <a name="localclientsettings-element"></a>Elemento \<localClientSettings>
Specifica le impostazioni di sicurezza di un client locale per questa associazione.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localClientSettings>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<security>
   <localClientSettings cacheCookies="Boolean"
                        cookieRenewalThresholdPercentage="Integer"
                        detectReplays="Boolean"
                        maxClockSkew="TimeSpan"
                        maxCookieCachingTime="TimeSpan"
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
|`cacheCookies`|Valore booleano che specifica se è attivata la memorizzazione dei cookie nella cache. Il valore predefinito è `false`.|  
|`cookieRenewalThresholdPercentage`|Un numero intero che specifica la percentuale massima di cookie che possono essere rinnovati. Questo valore deve essere compreso tra 0 e 100 inclusi. Il valore predefinito è 90.|  
|`detectReplays`|Valore booleano che specifica se gli attacchi di tipo replay contro il canale vengono rilevati e gestiti automaticamente. Il valore predefinito è `false`.|  
|`maxClockSkew`|<xref:System.TimeSpan> specifica la differenza massima di tempo tra gli orologi di sistema delle due parti che stanno comunicando. Il valore predefinito è "00:05:00".<br /><br /> Quando l'impostazione di questo valore è quella predefinita, il destinatario accetta i messaggi con timestamp relativi all'ora di invio precedenti o successivi all'ora in cui il messaggio è stato ricevuto. I messaggi che non passano i test dell'ora di invio vengono rifiutati. Questa impostazione viene usata in combinazione con l'attributo `replayWindow`.|  
|`maxCookieCachingTime`|<xref:System.TimeSpan> specifica la durata massima dei cookie. Il valore predefinito è "10675199.02:48:05.4775807".|  
|`reconnectTransportOnFailure`|Valore booleano che specifica se le connessioni che usano WS-Reliable Messaging tenteranno la riconnessione in caso di errori del trasporto. L'impostazione predefinita è `true`, la quale significa un numero infinito di tentativi di riconnessione. Il ciclo viene interrotto dal timeout di inattività che fa sì che il canale generi un'eccezione quando la riconnessione non è possibile.|  
|`replayCacheSize`|Un numero intero positivo che specifica il numero di parametri nonce da usare per il rilevamento di attacchi di tipo replay. Se questo limite viene superato, il nonce meno recente viene rimosso e viene creato un nuovo nonce per il messaggio nuovo. Il valore predefinito è 500000.|  
|`replayWindow`|<xref:System.TimeSpan> specifica la durata di validità dei singoli nonce dei messaggi.<br /><br /> Dopo questa durata, un messaggio inviato con lo stesso nonce di quello inviato precedentemente non verrà accettato. Questo attributo viene usato in combinazione con l'attributo `maxClockSkew` per impedire attacchi di tipo replay. L'autore di un attacco può replicare un messaggio dopo che la finestra di replay è scaduta. Questo messaggio, tuttavia, non supererebbe il test `maxClockSkew` che rifiuta i messaggi con timestamp relativi all'ora di invio che differiscono di un tempo specificato in più o in meno rispetto all'ora in cui il messaggio è stato ricevuto.|  
|`sessionKeyRenewalInterval`|<xref:System.TimeSpan> specifica l'intervallo di tempo dopo il quale l'iniziatore rinnoverà la chiave per la sessione di sicurezza. L'impostazione predefinita è "10:00:00".|  
|`sessionKeyRolloverInterval`|<xref:System.TimeSpan> specifica l'intervallo di tempo per il quale la chiave della sessione precedente è valida nei messaggi in arrivo durante un rinnovo della chiave. L'impostazione predefinita è "00:05:00".<br /><br /> Durante il rinnovo della chiave, client e server devono inviare i messaggi usando sempre la chiave disponibile più recente. Entrambe le parti accetteranno i messaggi in arrivo protetti con la chiave della sessione precedente fino alla scadenza del tempo di sostituzione.|  
|`timestampValidityDuration`|<xref:System.TimeSpan> positivo che specifica il periodo di validità di un timestamp. L'impostazione predefinita è "00:15:00".|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|Specifica le opzioni di sicurezza di un'associazione personalizzata.|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|Specifica i valori predefiniti usati per iniziare un servizio di conversazione protetta.|  
  
## <a name="remarks"></a>Commenti  
 Le impostazioni sono locali nel senso che non sono derivate dai criteri di sicurezza del servizio.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Binding](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Procedura: creare un'associazione personalizzata usando SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Sicurezza delle associazioni personalizzate](../../../wcf/samples/custom-binding-security.md)
