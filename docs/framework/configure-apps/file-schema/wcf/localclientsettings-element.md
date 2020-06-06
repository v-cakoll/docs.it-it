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
# <a name="localclientsettings-element"></a><span data-ttu-id="dab11-102">Elemento \<localClientSettings></span><span class="sxs-lookup"><span data-stu-id="dab11-102">\<localClientSettings> element</span></span>
<span data-ttu-id="dab11-103">Specifica le impostazioni di sicurezza di un client locale per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="dab11-103">Specifies the security settings of a local client for this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="dab11-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dab11-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dab11-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dab11-105">Attributes and Elements</span></span>  
 <span data-ttu-id="dab11-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dab11-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dab11-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="dab11-107">Attributes</span></span>  
  
|<span data-ttu-id="dab11-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="dab11-108">Attribute</span></span>|<span data-ttu-id="dab11-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dab11-109">Description</span></span>|  
|---------------|-----------------|  
|`cacheCookies`|<span data-ttu-id="dab11-110">Valore booleano che specifica se è attivata la memorizzazione dei cookie nella cache.</span><span class="sxs-lookup"><span data-stu-id="dab11-110">A Boolean value that specifies whether cookie caching is enabled.</span></span> <span data-ttu-id="dab11-111">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="dab11-111">The default is `false`.</span></span>|  
|`cookieRenewalThresholdPercentage`|<span data-ttu-id="dab11-112">Un numero intero che specifica la percentuale massima di cookie che possono essere rinnovati.</span><span class="sxs-lookup"><span data-stu-id="dab11-112">An integer that specifies the maximum percentage of cookies that can be renewed.</span></span> <span data-ttu-id="dab11-113">Questo valore deve essere compreso tra 0 e 100 inclusi.</span><span class="sxs-lookup"><span data-stu-id="dab11-113">This value should be between 0 and 100 inclusively.</span></span> <span data-ttu-id="dab11-114">Il valore predefinito è 90.</span><span class="sxs-lookup"><span data-stu-id="dab11-114">The default is 90.</span></span>|  
|`detectReplays`|<span data-ttu-id="dab11-115">Valore booleano che specifica se gli attacchi di tipo replay contro il canale vengono rilevati e gestiti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dab11-115">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="dab11-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="dab11-116">The default is `false`.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="dab11-117"><xref:System.TimeSpan> specifica la differenza massima di tempo tra gli orologi di sistema delle due parti che stanno comunicando.</span><span class="sxs-lookup"><span data-stu-id="dab11-117">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="dab11-118">Il valore predefinito è "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="dab11-118">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="dab11-119">Quando l'impostazione di questo valore è quella predefinita, il destinatario accetta i messaggi con timestamp relativi all'ora di invio precedenti o successivi all'ora in cui il messaggio è stato ricevuto.</span><span class="sxs-lookup"><span data-stu-id="dab11-119">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="dab11-120">I messaggi che non passano i test dell'ora di invio vengono rifiutati.</span><span class="sxs-lookup"><span data-stu-id="dab11-120">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="dab11-121">Questa impostazione viene usata in combinazione con l'attributo `replayWindow`.</span><span class="sxs-lookup"><span data-stu-id="dab11-121">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxCookieCachingTime`|<span data-ttu-id="dab11-122"><xref:System.TimeSpan> specifica la durata massima dei cookie.</span><span class="sxs-lookup"><span data-stu-id="dab11-122">A <xref:System.TimeSpan> that specifies the maximum lifetime of cookies.</span></span> <span data-ttu-id="dab11-123">Il valore predefinito è "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="dab11-123">The default value is "10675199.02:48:05.4775807".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="dab11-124">Valore booleano che specifica se le connessioni che usano WS-Reliable Messaging tenteranno la riconnessione in caso di errori del trasporto.</span><span class="sxs-lookup"><span data-stu-id="dab11-124">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="dab11-125">L'impostazione predefinita è `true`, la quale significa un numero infinito di tentativi di riconnessione.</span><span class="sxs-lookup"><span data-stu-id="dab11-125">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="dab11-126">Il ciclo viene interrotto dal timeout di inattività che fa sì che il canale generi un'eccezione quando la riconnessione non è possibile.</span><span class="sxs-lookup"><span data-stu-id="dab11-126">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="dab11-127">Un numero intero positivo che specifica il numero di parametri nonce da usare per il rilevamento di attacchi di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="dab11-127">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="dab11-128">Se questo limite viene superato, il nonce meno recente viene rimosso e viene creato un nuovo nonce per il messaggio nuovo.</span><span class="sxs-lookup"><span data-stu-id="dab11-128">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="dab11-129">Il valore predefinito è 500000.</span><span class="sxs-lookup"><span data-stu-id="dab11-129">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="dab11-130"><xref:System.TimeSpan> specifica la durata di validità dei singoli nonce dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="dab11-130">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="dab11-131">Dopo questa durata, un messaggio inviato con lo stesso nonce di quello inviato precedentemente non verrà accettato.</span><span class="sxs-lookup"><span data-stu-id="dab11-131">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="dab11-132">Questo attributo viene usato in combinazione con l'attributo `maxClockSkew` per impedire attacchi di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="dab11-132">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="dab11-133">L'autore di un attacco può replicare un messaggio dopo che la finestra di replay è scaduta.</span><span class="sxs-lookup"><span data-stu-id="dab11-133">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="dab11-134">Questo messaggio, tuttavia, non supererebbe il test `maxClockSkew` che rifiuta i messaggi con timestamp relativi all'ora di invio che differiscono di un tempo specificato in più o in meno rispetto all'ora in cui il messaggio è stato ricevuto.</span><span class="sxs-lookup"><span data-stu-id="dab11-134">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="dab11-135"><xref:System.TimeSpan> specifica l'intervallo di tempo dopo il quale l'iniziatore rinnoverà la chiave per la sessione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dab11-135">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="dab11-136">L'impostazione predefinita è "10:00:00".</span><span class="sxs-lookup"><span data-stu-id="dab11-136">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="dab11-137"><xref:System.TimeSpan> specifica l'intervallo di tempo per il quale la chiave della sessione precedente è valida nei messaggi in arrivo durante un rinnovo della chiave.</span><span class="sxs-lookup"><span data-stu-id="dab11-137">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="dab11-138">L'impostazione predefinita è "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="dab11-138">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="dab11-139">Durante il rinnovo della chiave, client e server devono inviare i messaggi usando sempre la chiave disponibile più recente.</span><span class="sxs-lookup"><span data-stu-id="dab11-139">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="dab11-140">Entrambe le parti accetteranno i messaggi in arrivo protetti con la chiave della sessione precedente fino alla scadenza del tempo di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="dab11-140">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="dab11-141"><xref:System.TimeSpan> positivo che specifica il periodo di validità di un timestamp.</span><span class="sxs-lookup"><span data-stu-id="dab11-141">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="dab11-142">L'impostazione predefinita è "00:15:00".</span><span class="sxs-lookup"><span data-stu-id="dab11-142">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dab11-143">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dab11-143">Child Elements</span></span>  
 <span data-ttu-id="dab11-144">nessuno</span><span class="sxs-lookup"><span data-stu-id="dab11-144">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dab11-145">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dab11-145">Parent Elements</span></span>  
  
|<span data-ttu-id="dab11-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="dab11-146">Element</span></span>|<span data-ttu-id="dab11-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dab11-147">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="dab11-148">Specifica le opzioni di sicurezza di un'associazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dab11-148">Specifies the security options for a custom binding.</span></span>|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="dab11-149">Specifica i valori predefiniti usati per iniziare un servizio di conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="dab11-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dab11-150">Commenti</span><span class="sxs-lookup"><span data-stu-id="dab11-150">Remarks</span></span>  
 <span data-ttu-id="dab11-151">Le impostazioni sono locali nel senso che non sono derivate dai criteri di sicurezza del servizio.</span><span class="sxs-lookup"><span data-stu-id="dab11-151">The settings are local in the sense that they are not settings derived from the security policy of the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab11-152">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="dab11-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="dab11-153">Binding</span><span class="sxs-lookup"><span data-stu-id="dab11-153">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dab11-154">Estensione delle associazioni</span><span class="sxs-lookup"><span data-stu-id="dab11-154">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="dab11-155">Associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="dab11-155">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="dab11-156">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dab11-156">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="dab11-157">Sicurezza delle associazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="dab11-157">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
