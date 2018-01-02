---
title: '&lt;security&gt; di &lt;netTcpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 08e9f1f3b2145d94f491933639211a6eabd3c9fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltnettcpbindinggt"></a><span data-ttu-id="60096-102">&lt;security&gt; di &lt;netTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="60096-102">&lt;security&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="60096-103">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="60096-103">Defines the security settings for a binding.</span></span>  
  
 <span data-ttu-id="60096-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="60096-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="60096-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="60096-105">\<bindings></span></span>  
<span data-ttu-id="60096-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="60096-106">\<netTcpBinding></span></span>  
<span data-ttu-id="60096-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="60096-107">\<binding></span></span>  
<span data-ttu-id="60096-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="60096-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60096-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60096-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">  
   <transport  
      clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
           protectionLevel="None/Sign/EncryptAndSign" />  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60096-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="60096-110">Attributes and Elements</span></span>  
 <span data-ttu-id="60096-111">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="60096-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60096-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="60096-112">Attributes</span></span>  
  
|<span data-ttu-id="60096-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="60096-113">Attribute</span></span>|<span data-ttu-id="60096-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60096-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60096-115">modalità</span><span class="sxs-lookup"><span data-stu-id="60096-115">mode</span></span>|<span data-ttu-id="60096-116">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="60096-116">Optional.</span></span> <span data-ttu-id="60096-117">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="60096-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="60096-118">I valori validi sono riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="60096-118">Valid values are shown below.</span></span> <span data-ttu-id="60096-119">Il valore predefinito è `Transport`.</span><span class="sxs-lookup"><span data-stu-id="60096-119">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="60096-120">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="60096-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="60096-121">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="60096-121">mode Attribute</span></span>  
  
|<span data-ttu-id="60096-122">Valore</span><span class="sxs-lookup"><span data-stu-id="60096-122">Value</span></span>|<span data-ttu-id="60096-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60096-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60096-124">None</span><span class="sxs-lookup"><span data-stu-id="60096-124">None</span></span>|<span data-ttu-id="60096-125">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="60096-125">Security is disabled.</span></span>|  
|<span data-ttu-id="60096-126">Trasporto</span><span class="sxs-lookup"><span data-stu-id="60096-126">Transport</span></span>|<span data-ttu-id="60096-127">La sicurezza del trasporto è fornita usando TLS su TCP o SPNego.</span><span class="sxs-lookup"><span data-stu-id="60096-127">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="60096-128">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="60096-128">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="60096-129">Con questa modalità è possibile controllare il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="60096-129">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="60096-130">Messaggio</span><span class="sxs-lookup"><span data-stu-id="60096-130">Message</span></span>|<span data-ttu-id="60096-131">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="60096-131">Security is provided using SOAP message security.</span></span> <span data-ttu-id="60096-132">Per impostazione predefinita, il corpo SOAP viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="60096-132">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="60096-133">Questa modalità offre varie funzionalità, ad esempio se le credenziali del servizio sono disponibili per client fuori banda, la suite di algoritmi usare e il livello di protezione per applicare al corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="60096-133">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="60096-134">L'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="60096-134">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="60096-135">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="60096-135">TransportWithMessageCredential</span></span>|<span data-ttu-id="60096-136">La sicurezza del trasporto è abbinata alla sicurezza del messaggio.</span><span class="sxs-lookup"><span data-stu-id="60096-136">Transport security is coupled with message security.</span></span> <span data-ttu-id="60096-137">La sicurezza del trasporto è fornita da TLS su TCP o SPNego e assicura integrità, riservatezza e autenticazione server.</span><span class="sxs-lookup"><span data-stu-id="60096-137">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="60096-138">La sicurezza del messaggio SOAP fornisce l'autenticazione del client.</span><span class="sxs-lookup"><span data-stu-id="60096-138">SOAP message security provides client authentication.</span></span> <span data-ttu-id="60096-139">Per impostazione predefinita, l'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="60096-139">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60096-140">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="60096-140">Child Elements</span></span>  
  
|<span data-ttu-id="60096-141">Elemento</span><span class="sxs-lookup"><span data-stu-id="60096-141">Element</span></span>|<span data-ttu-id="60096-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60096-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60096-143">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="60096-143">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)|<span data-ttu-id="60096-144">Definisce le impostazioni di sicurezza per il trasporto.</span><span class="sxs-lookup"><span data-stu-id="60096-144">Defines the security settings for the transport.</span></span> <span data-ttu-id="60096-145">L'elemento è di tipo <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="60096-145">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[<span data-ttu-id="60096-146">\<messaggio ></span><span class="sxs-lookup"><span data-stu-id="60096-146">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)|<span data-ttu-id="60096-147">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="60096-147">Defines the security settings for the message.</span></span> <span data-ttu-id="60096-148">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span><span class="sxs-lookup"><span data-stu-id="60096-148">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="60096-149">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="60096-149">Parent Elements</span></span>  
  
|<span data-ttu-id="60096-150">Elemento</span><span class="sxs-lookup"><span data-stu-id="60096-150">Element</span></span>|<span data-ttu-id="60096-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60096-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60096-152">associazione</span><span class="sxs-lookup"><span data-stu-id="60096-152">binding</span></span>|<span data-ttu-id="60096-153">L'elemento di associazione di [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="60096-153">The binding element of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60096-154">Note</span><span class="sxs-lookup"><span data-stu-id="60096-154">Remarks</span></span>  
 <span data-ttu-id="60096-155">Ognuna delle associazioni standard fornisce parametri per controllare i requisiti di sicurezza di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="60096-155">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="60096-156">Alcuni esempi tipici di elementi controllati da questi parametri sono la modalità di sicurezza che determina se la sicurezza è a livello di messaggio o a livello di trasporto e la scelta del tipo di credenziale client.</span><span class="sxs-lookup"><span data-stu-id="60096-156">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="60096-157">L'infrastruttura crea uno stack di canali con il tipo di sicurezza appropriato a partire dal gruppo di opzioni impostate tramite questi parametri.</span><span class="sxs-lookup"><span data-stu-id="60096-157">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="60096-158">Le associazioni fornite da Windows Communication Foundation (WCF) formano un insieme progettato per soddisfare alcuni dei requisiti di scenario più comuni.</span><span class="sxs-lookup"><span data-stu-id="60096-158">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="60096-159">Ognuna di queste associazioni consente la definizione mirata dei requisiti di sicurezza relativi ad alcuni scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="60096-159">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="60096-160">Questo elemento di configurazione fornisce le specifiche di sicurezza per  `netTcpBinding`.</span><span class="sxs-lookup"><span data-stu-id="60096-160">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="60096-161">Si tratta di un'associazione protetta, affidabile, ottimizzata e adatta per le comunicazioni fra computer.</span><span class="sxs-lookup"><span data-stu-id="60096-161">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="60096-162">Tale associazione crea per impostazione predefinita uno stack di comunicazione in fase di esecuzione che, oltre a implementare la codifica binaria dei messaggi, usa il protocollo TCP per l'invio dei messaggi, Windows Security per proteggere e autenticare i messaggi e WS-ReliableMessaging per garantire l'affidabilità delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="60096-162">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60096-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60096-163">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpSecurity>  
 <xref:System.ServiceModel.NetTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>  
 [<span data-ttu-id="60096-164">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="60096-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="60096-165">Associazioni</span><span class="sxs-lookup"><span data-stu-id="60096-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="60096-166">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="60096-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="60096-167">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="60096-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="60096-168">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="60096-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
