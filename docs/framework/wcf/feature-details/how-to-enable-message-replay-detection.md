---
title: 'Procedura: attivare il rilevamento di attacchi di tipo replay dei messaggi'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF security
- replay detection [WCF]
- WCF, custom bindings
- WCF, security
ms.assetid: 8b847e91-69a3-49e1-9e5f-0c455e50d804
ms.openlocfilehash: 05bcddabf625e478616cce39f08b0ff8af282716
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184944"
---
# <a name="how-to-enable-message-replay-detection"></a><span data-ttu-id="881ff-102">Procedura: attivare il rilevamento di attacchi di tipo replay dei messaggi</span><span class="sxs-lookup"><span data-stu-id="881ff-102">How to: Enable Message Replay Detection</span></span>
<span data-ttu-id="881ff-103">Un attacco di tipo replay si verifica quando l'autore dell'attacco copia un flusso di messaggi tra due interessati e lo riproduce nei confronti di uno o più degli interessati.</span><span class="sxs-lookup"><span data-stu-id="881ff-103">A replay attack occurs when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties.</span></span> <span data-ttu-id="881ff-104">Se l'attacco non viene contrastato, i computer colpiti elaboreranno il flusso come se i messaggi fossero legittimi, determinando una serie di conseguenze negative, ad esempio ordini ridondanti di un elemento.</span><span class="sxs-lookup"><span data-stu-id="881ff-104">Unless mitigated, the computers subject to the attack will process the stream as legitimate messages, resulting in a range of bad consequences, such as redundant orders of an item.</span></span>  
  
 <span data-ttu-id="881ff-105">Per ulteriori informazioni sul rilevamento della riproduzione dei messaggi, vedere [Rilevamento della riproduzione dei](https://docs.microsoft.com/previous-versions/msp-n-p/ff649371(v=pandp.10))messaggi .</span><span class="sxs-lookup"><span data-stu-id="881ff-105">For more information about message replay detection, see [Message Replay Detection](https://docs.microsoft.com/previous-versions/msp-n-p/ff649371(v=pandp.10)).</span></span>  
  
 <span data-ttu-id="881ff-106">Nella procedura seguente vengono illustrate varie proprietà che è possibile utilizzare per controllare il rilevamento della riproduzione tramite Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="881ff-106">The following procedure demonstrates various properties that you can use to control replay detection using Windows Communication Foundation (WCF).</span></span>  
  
### <a name="to-control-replay-detection-on-the-client-using-code"></a><span data-ttu-id="881ff-107">Per controllare il rilevamento di attacchi di tipo replay nel client mediante il codice</span><span class="sxs-lookup"><span data-stu-id="881ff-107">To control replay detection on the client using code</span></span>  
  
1. <span data-ttu-id="881ff-108">Creare un elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> da utilizzare in una classe <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="881ff-108">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span> <span data-ttu-id="881ff-109">Per ulteriori informazioni, vedere [Procedura: creare un'associazione personalizzata utilizzando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="881ff-109">For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="881ff-110">Nell'esempio seguente si utilizza un elemento <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> creato con il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> della classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="881ff-110">The following example uses a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> created with the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span>  
  
2. <span data-ttu-id="881ff-111">Utilizzare la proprietà <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> per restituire un riferimento alla classe <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> e impostare le proprietà seguenti, in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="881ff-111">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class and set any of the following properties, as appropriate:</span></span>  
  
    1. <span data-ttu-id="881ff-112">`DetectReplay`.</span><span class="sxs-lookup"><span data-stu-id="881ff-112">`DetectReplay`.</span></span> <span data-ttu-id="881ff-113">Valore booleano.</span><span class="sxs-lookup"><span data-stu-id="881ff-113">A Boolean value.</span></span> <span data-ttu-id="881ff-114">Determina se il client deve rilevare attacchi di tipo replay dal server.</span><span class="sxs-lookup"><span data-stu-id="881ff-114">This governs whether the client should detect replays from the server.</span></span> <span data-ttu-id="881ff-115">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="881ff-115">The default is `true`.</span></span>  
  
    2. <span data-ttu-id="881ff-116">`MaxClockSkew`.</span><span class="sxs-lookup"><span data-stu-id="881ff-116">`MaxClockSkew`.</span></span> <span data-ttu-id="881ff-117">Valore <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="881ff-117">A <xref:System.TimeSpan> value.</span></span> <span data-ttu-id="881ff-118">Determina lo sfasamento temporale tollerato dal meccanismo di replay tra client e server.</span><span class="sxs-lookup"><span data-stu-id="881ff-118">Governs how much time skew the replay mechanism can tolerate between the client and the server.</span></span> <span data-ttu-id="881ff-119">Il meccanismo di sicurezza esamina il timestamp inviato e stabilisce se è troppo vecchio.</span><span class="sxs-lookup"><span data-stu-id="881ff-119">The security mechanism examines the time stamp sent and determines whether it was sent too far back in the past.</span></span> <span data-ttu-id="881ff-120">Il valore predefinito è 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="881ff-120">The default is 5 minutes.</span></span>  
  
    3. <span data-ttu-id="881ff-121">`ReplayWindow`.</span><span class="sxs-lookup"><span data-stu-id="881ff-121">`ReplayWindow`.</span></span> <span data-ttu-id="881ff-122">Valore `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="881ff-122">A `TimeSpan` value.</span></span> <span data-ttu-id="881ff-123">Determina quanto tempo un messaggio può permanere nella rete dopo l'invio dal server (tramite intermediari) prima di raggiungere il client.</span><span class="sxs-lookup"><span data-stu-id="881ff-123">This governs how long a message can live in the network after the server sends it (through intermediaries) before reaching the client.</span></span> <span data-ttu-id="881ff-124">Il client tiene traccia delle firme dei messaggi inviati all'interno dell'ultimo `ReplayWindow` a scopo di rilevamento di attacchi di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="881ff-124">The client tracks the signatures of the messages sent within the latest `ReplayWindow` for the purposes of replay detection.</span></span>  
  
    4. <span data-ttu-id="881ff-125">`ReplayCacheSize`.</span><span class="sxs-lookup"><span data-stu-id="881ff-125">`ReplayCacheSize`.</span></span> <span data-ttu-id="881ff-126">Valore intero.</span><span class="sxs-lookup"><span data-stu-id="881ff-126">An integer value.</span></span> <span data-ttu-id="881ff-127">Il client archivia le firme del messaggio in una cache.</span><span class="sxs-lookup"><span data-stu-id="881ff-127">The client stores the signatures of the message in a cache.</span></span> <span data-ttu-id="881ff-128">Questa impostazione specifica quante firme che possono essere archiviate nella cache.</span><span class="sxs-lookup"><span data-stu-id="881ff-128">This setting specifies how many signatures the cache can store.</span></span> <span data-ttu-id="881ff-129">Se il numero dei messaggi inviati all'interno dell'ultima finestra di replay raggiunge il limite della cache, i messaggi nuovi vengono respinti finché le firme più vecchie contenute nella cache non raggiungono il limite di tempo.</span><span class="sxs-lookup"><span data-stu-id="881ff-129">If the number of messages sent within the last replay window reaches the cache limit, new messages are rejected until the oldest cached signatures reach the time limit.</span></span> <span data-ttu-id="881ff-130">Il valore predefinito è 500000.</span><span class="sxs-lookup"><span data-stu-id="881ff-130">The default is 500000.</span></span>  
  
### <a name="to-control-replay-detection-on-the-service-using-code"></a><span data-ttu-id="881ff-131">Per controllare il rilevamento di attacchi di tipo replay nel servizio mediante il codice</span><span class="sxs-lookup"><span data-stu-id="881ff-131">To control replay detection on the service using code</span></span>  
  
1. <span data-ttu-id="881ff-132">Creare un elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> da utilizzare in una classe <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="881ff-132">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
2. <span data-ttu-id="881ff-133">Utilizzare la proprietà <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> per restituire un riferimento alla classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> e impostare le proprietà come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="881ff-133">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class, and set the properties as described previously.</span></span>  
  
### <a name="to-control-replay-detection-in-configuration-for-the-client-or-service"></a><span data-ttu-id="881ff-134">Per controllare il rilevamento di attacchi di tipo replay nella configurazione per il client o il servizio</span><span class="sxs-lookup"><span data-stu-id="881ff-134">To control replay detection in configuration for the client or service</span></span>  
  
1. <span data-ttu-id="881ff-135">Creare un [ \<>customBinding ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="881ff-135">Create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
2. <span data-ttu-id="881ff-136">Creare un elemento `<security>`.</span><span class="sxs-lookup"><span data-stu-id="881ff-136">Create a `<security>` element.</span></span>  
  
3. <span data-ttu-id="881ff-137">Creare [ \<un>localClientSettings>o](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) [ \<localServiceSettings ](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md).</span><span class="sxs-lookup"><span data-stu-id="881ff-137">Create a [\<localClientSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md) or [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md).</span></span>  
  
4. <span data-ttu-id="881ff-138">Se necessario, impostare gli attributi seguenti: `detectReplays`, `maxClockSkew`, `replayWindow` e `replayCacheSize`.</span><span class="sxs-lookup"><span data-stu-id="881ff-138">Set the following attribute values, as appropriate: `detectReplays`, `maxClockSkew`, `replayWindow`, and `replayCacheSize`.</span></span> <span data-ttu-id="881ff-139">Nell'esempio seguente vengono impostati entrambi gli elementi `<localServiceSettings>`.</span><span class="sxs-lookup"><span data-stu-id="881ff-139">The following example sets the attributes of both a `<localServiceSettings>` and a `<localClientSettings>` element:</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="NewBinding0">  
       <textMessageEncoding />  
        <security>  
         <localClientSettings
          replayCacheSize="800000"
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
         <localServiceSettings
          replayCacheSize="800000"
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
        <secureConversationBootstrap />  
       </security>  
      <httpTransport />  
     </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="881ff-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="881ff-140">Example</span></span>  
 <span data-ttu-id="881ff-141">Nell'esempio seguente viene creata una classe <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> utilizzando il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> e vengono impostate le proprietà di replay dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="881ff-141">The following example creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> using the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> method, and sets the replay properties of the binding.</span></span>  
  
 [!code-csharp[c_ReplayDetection#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_replaydetection/cs/source.cs#1)]
 [!code-vb[c_ReplayDetection#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_replaydetection/vb/source.vb#1)]  
  
## <a name="scope-of-replay-message-security-only"></a><span data-ttu-id="881ff-142">Ambito di attacchi di tipo replay: solo sicurezza messaggi</span><span class="sxs-lookup"><span data-stu-id="881ff-142">Scope of Replay: Message Security Only</span></span>  
 <span data-ttu-id="881ff-143">Si noti che le procedure seguenti si riferiscono solo alla modalità di sicurezza messaggio.</span><span class="sxs-lookup"><span data-stu-id="881ff-143">Note that the following procedures apply only to Message security mode.</span></span> <span data-ttu-id="881ff-144">Per le modalità di trasporto e di trasporto con credenziali messaggio, i meccanismi di trasporto rilevano gli attacchi di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="881ff-144">For Transport and Transport with Message Credential modes, the transport mechanisms detect replays.</span></span>  
  
## <a name="secure-conversation-notes"></a><span data-ttu-id="881ff-145">Note sulla conversazione protetta</span><span class="sxs-lookup"><span data-stu-id="881ff-145">Secure Conversation Notes</span></span>  
 <span data-ttu-id="881ff-146">Per le associazioni che consentono conversazioni protette, è possibile regolare queste impostazioni sia per il canale dell'applicazione che per l'associazione del bootstrap della conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="881ff-146">For bindings that enable secure conversations, you can adjust these settings both for the application channel as well as for the secure conversation bootstrap binding.</span></span> <span data-ttu-id="881ff-147">È ad esempio possibile disattivare gli attacchi di tipo replay per il canale dell'applicazione abilitandoli tuttavia per il canale del bootstrap che stabilisce la conversazione protetta.</span><span class="sxs-lookup"><span data-stu-id="881ff-147">For example, you can turn off replays for the application channel but enable them for the bootstrap channel that establishes the secure conversation.</span></span>  
  
 <span data-ttu-id="881ff-148">Se non si utilizzano sessioni di conversazione protetta, il rilevamento di attacchi di tipo replay non garantisce il rilevamento di attacchi in scenari di server farm e quando il processo viene riciclato.</span><span class="sxs-lookup"><span data-stu-id="881ff-148">If you do not use secure conversation sessions, replay detection does not guarantee detecting replays in server farm scenarios and when the process is recycled.</span></span> <span data-ttu-id="881ff-149">Ciò vale per le associazioni fornite dal sistema seguenti:</span><span class="sxs-lookup"><span data-stu-id="881ff-149">This applies to the following system-provided bindings:</span></span>  
  
- <span data-ttu-id="881ff-150"><xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="881ff-150"><xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
- <span data-ttu-id="881ff-151"><xref:System.ServiceModel.WSHttpBinding> con la proprietà <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> impostata su `false`.</span><span class="sxs-lookup"><span data-stu-id="881ff-151"><xref:System.ServiceModel.WSHttpBinding> with the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property set to `false`.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="881ff-152">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="881ff-152">Compiling the Code</span></span>  
  
- <span data-ttu-id="881ff-153">Per compilare il codice sono necessari gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="881ff-153">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
## <a name="see-also"></a><span data-ttu-id="881ff-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="881ff-154">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="881ff-155">Conversazioni e sessioni protette</span><span class="sxs-lookup"><span data-stu-id="881ff-155">Secure Conversations and Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)
- [<span data-ttu-id="881ff-156">\<>localClientSettings</span><span class="sxs-lookup"><span data-stu-id="881ff-156">\<localClientSettings></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)
- [<span data-ttu-id="881ff-157">Procedura: creare un'associazione personalizzata usando SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="881ff-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
