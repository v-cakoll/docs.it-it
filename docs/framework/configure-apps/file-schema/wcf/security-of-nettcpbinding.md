---
title: <security> di <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: aa01e906ddd2f15007c72bfc2a45122cfb15ba2c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736366"
---
# <a name="security-of-nettcpbinding"></a><span data-ttu-id="6b895-102">\<security> di \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="6b895-102">\<security> of \<netTcpBinding></span></span>
<span data-ttu-id="6b895-103">Definisce le impostazioni di sicurezza per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="6b895-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="6b895-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b895-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b895-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6b895-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6b895-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6b895-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b895-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="6b895-107">Attributes</span></span>  
  
|<span data-ttu-id="6b895-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="6b895-108">Attribute</span></span>|<span data-ttu-id="6b895-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b895-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b895-110">mode</span><span class="sxs-lookup"><span data-stu-id="6b895-110">mode</span></span>|<span data-ttu-id="6b895-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="6b895-111">Optional.</span></span> <span data-ttu-id="6b895-112">Specifica il tipo di sicurezza applicata.</span><span class="sxs-lookup"><span data-stu-id="6b895-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="6b895-113">I valori validi sono riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="6b895-113">Valid values are shown below.</span></span> <span data-ttu-id="6b895-114">Il valore predefinito è `Transport`.</span><span class="sxs-lookup"><span data-stu-id="6b895-114">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="6b895-115">L'attributo è di tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="6b895-115">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="6b895-116">Attributo mode</span><span class="sxs-lookup"><span data-stu-id="6b895-116">mode Attribute</span></span>  
  
|<span data-ttu-id="6b895-117">Valore</span><span class="sxs-lookup"><span data-stu-id="6b895-117">Value</span></span>|<span data-ttu-id="6b895-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b895-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6b895-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="6b895-119">None</span></span>|<span data-ttu-id="6b895-120">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="6b895-120">Security is disabled.</span></span>|  
|<span data-ttu-id="6b895-121">Trasporto</span><span class="sxs-lookup"><span data-stu-id="6b895-121">Transport</span></span>|<span data-ttu-id="6b895-122">La sicurezza del trasporto è fornita usando TLS su TCP o SPNego.</span><span class="sxs-lookup"><span data-stu-id="6b895-122">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="6b895-123">Può essere necessario che il servizio sia configurato con certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="6b895-123">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="6b895-124">È possibile controllare il livello di protezione con questa modalità.</span><span class="sxs-lookup"><span data-stu-id="6b895-124">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="6b895-125">Message</span><span class="sxs-lookup"><span data-stu-id="6b895-125">Message</span></span>|<span data-ttu-id="6b895-126">La sicurezza è fornita mediante la sicurezza dei messaggi SOAP.</span><span class="sxs-lookup"><span data-stu-id="6b895-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="6b895-127">Per impostazione predefinita, il corpo SOAP viene crittografato e firmato.</span><span class="sxs-lookup"><span data-stu-id="6b895-127">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="6b895-128">Questa modalità offre varie funzionalità, ad esempio se le credenziali del servizio sono disponibili per client fuori banda, il gruppo di algoritmi da usare e il livello di protezione da applicare al corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="6b895-128">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="6b895-129">L'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="6b895-129">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="6b895-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="6b895-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="6b895-131">La sicurezza del trasporto è abbinata alla sicurezza del messaggio.</span><span class="sxs-lookup"><span data-stu-id="6b895-131">Transport security is coupled with message security.</span></span> <span data-ttu-id="6b895-132">La sicurezza del trasporto è fornita da TLS su TCP o SPNego e assicura integrità, riservatezza e autenticazione server.</span><span class="sxs-lookup"><span data-stu-id="6b895-132">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="6b895-133">La sicurezza del messaggio SOAP fornisce l'autenticazione del client.</span><span class="sxs-lookup"><span data-stu-id="6b895-133">SOAP message security provides client authentication.</span></span> <span data-ttu-id="6b895-134">Per impostazione predefinita, l'autenticazione client viene eseguita una volta per sessione e i risultati vengono memorizzati nella cache per la durata della sessione.</span><span class="sxs-lookup"><span data-stu-id="6b895-134">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b895-135">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6b895-135">Child Elements</span></span>  
  
|<span data-ttu-id="6b895-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b895-136">Element</span></span>|<span data-ttu-id="6b895-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b895-137">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|<span data-ttu-id="6b895-138">Definisce le impostazioni di sicurezza per il trasporto.</span><span class="sxs-lookup"><span data-stu-id="6b895-138">Defines the security settings for the transport.</span></span> <span data-ttu-id="6b895-139">L'elemento è di tipo <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="6b895-139">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[\<message>](message-element-of-nettcpbinding.md)|<span data-ttu-id="6b895-140">Definisce le impostazioni di sicurezza per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="6b895-140">Defines the security settings for the message.</span></span> <span data-ttu-id="6b895-141">L'elemento è di tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span><span class="sxs-lookup"><span data-stu-id="6b895-141">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b895-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6b895-142">Parent Elements</span></span>  
  
|<span data-ttu-id="6b895-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b895-143">Element</span></span>|<span data-ttu-id="6b895-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6b895-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b895-145">binding</span><span class="sxs-lookup"><span data-stu-id="6b895-145">binding</span></span>|<span data-ttu-id="6b895-146">Elemento di associazione di [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6b895-146">The binding element of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b895-147">Commenti</span><span class="sxs-lookup"><span data-stu-id="6b895-147">Remarks</span></span>  
 <span data-ttu-id="6b895-148">Ognuna delle associazioni standard fornisce parametri per controllare i requisiti di sicurezza di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="6b895-148">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="6b895-149">Alcuni esempi tipici di elementi controllati da questi parametri sono la modalità di sicurezza che determina se la sicurezza è a livello di messaggio o a livello di trasporto e la scelta del tipo di credenziale client.</span><span class="sxs-lookup"><span data-stu-id="6b895-149">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="6b895-150">L'infrastruttura crea uno stack di canali con il tipo di sicurezza appropriato a partire dal gruppo di opzioni impostate tramite questi parametri.</span><span class="sxs-lookup"><span data-stu-id="6b895-150">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="6b895-151">Le associazioni fornite da Windows Communication Foundation (WCF) formano un insieme progettato per soddisfare alcuni dei requisiti di scenario più comuni.</span><span class="sxs-lookup"><span data-stu-id="6b895-151">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="6b895-152">Ognuna di queste associazioni consente la definizione mirata dei requisiti di sicurezza relativi ad alcuni scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="6b895-152">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="6b895-153">Questo elemento di configurazione fornisce le specifiche di sicurezza per  `netTcpBinding`.</span><span class="sxs-lookup"><span data-stu-id="6b895-153">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="6b895-154">Si tratta di un'associazione protetta, affidabile, ottimizzata e adatta per le comunicazioni fra computer.</span><span class="sxs-lookup"><span data-stu-id="6b895-154">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="6b895-155">Tale associazione crea per impostazione predefinita uno stack di comunicazione in fase di esecuzione che, oltre a implementare la codifica binaria dei messaggi, usa il protocollo TCP per l'invio dei messaggi, Windows Security per proteggere e autenticare i messaggi e WS-ReliableMessaging per garantire l'affidabilità delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="6b895-155">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b895-156">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6b895-156">See also</span></span>

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="6b895-157">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="6b895-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6b895-158">Binding</span><span class="sxs-lookup"><span data-stu-id="6b895-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6b895-159">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="6b895-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6b895-160">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="6b895-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
