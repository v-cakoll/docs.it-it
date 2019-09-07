---
title: <transport> di <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 41f11be9b4ae8f7a7535c9766965de8575cff784
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399302"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="2705b-102">\<transport> di \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="2705b-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="2705b-103">Definisce il tipo di requisiti di sicurezza a livello di messaggio per un endpoint configurato con [ \<NetTcpBinding >](nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2705b-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
<span data-ttu-id="2705b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2705b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2705b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2705b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2705b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2705b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2705b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NetTcpBinding >** ](nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2705b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)</span></span>\
<span data-ttu-id="2705b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="2705b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2705b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2705b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)</span></span>\
<span data-ttu-id="2705b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di trasporto**</span><span class="sxs-lookup"><span data-stu-id="2705b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2705b-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2705b-111">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential">
      <transport clientCredentialType="None|Windows|Certificate"
                 protectionLevel="None|Sign|EncryptAndSign"
                 sslProtocols="Tls|Tls11|Tls12">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2705b-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2705b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2705b-113">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2705b-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2705b-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="2705b-114">Attributes</span></span>  
  
|<span data-ttu-id="2705b-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="2705b-115">Attribute</span></span>|<span data-ttu-id="2705b-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2705b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2705b-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="2705b-117">clientCredentialType</span></span>|<span data-ttu-id="2705b-118">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2705b-118">Optional.</span></span> <span data-ttu-id="2705b-119">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="2705b-119">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="2705b-120">-Il valore predefinito è `Windows`.</span><span class="sxs-lookup"><span data-stu-id="2705b-120">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="2705b-121">: Questo attributo è di tipo <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="2705b-121">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="2705b-122">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="2705b-122">protectionLevel</span></span>|<span data-ttu-id="2705b-123">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2705b-123">Optional.</span></span> <span data-ttu-id="2705b-124">Definisce il livello di sicurezza del trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="2705b-124">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="2705b-125">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="2705b-125">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="2705b-126">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="2705b-126">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="2705b-127">Il valore predefinito è `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="2705b-127">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="2705b-128">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="2705b-128">sslProtocols</span></span>|<span data-ttu-id="2705b-129">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="2705b-129">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="2705b-130">Il valore predefinito è&#124;TLS&#124;Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="2705b-130">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="2705b-131">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="2705b-131">policyEnforcement</span></span>|<span data-ttu-id="2705b-132">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="2705b-132">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="2705b-133">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="2705b-133">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="2705b-134">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="2705b-134">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="2705b-135">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="2705b-135">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="2705b-136">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2705b-136">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="2705b-137">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="2705b-137">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2705b-138">Value</span><span class="sxs-lookup"><span data-stu-id="2705b-138">Value</span></span>|<span data-ttu-id="2705b-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2705b-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2705b-140">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2705b-140">None</span></span>|<span data-ttu-id="2705b-141">Il client è anonimo.</span><span class="sxs-lookup"><span data-stu-id="2705b-141">The client is anonymous.</span></span> <span data-ttu-id="2705b-142">Richiede un certificato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="2705b-142">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="2705b-143">Windows</span><span class="sxs-lookup"><span data-stu-id="2705b-143">Windows</span></span>|<span data-ttu-id="2705b-144">Specifica l'autenticazione Windows del client mediante la negoziazione SP (negoziazione Kerberos).</span><span class="sxs-lookup"><span data-stu-id="2705b-144">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="2705b-145">Certificato</span><span class="sxs-lookup"><span data-stu-id="2705b-145">Certificate</span></span>|<span data-ttu-id="2705b-146">Il client viene autenticato mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="2705b-146">The client is authenticated using a certificate.</span></span> <span data-ttu-id="2705b-147">Viene usata la negoziazione SSL ed è necessario un certificato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="2705b-147">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="2705b-148">Attributo protectionLevel</span><span class="sxs-lookup"><span data-stu-id="2705b-148">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="2705b-149">Value</span><span class="sxs-lookup"><span data-stu-id="2705b-149">Value</span></span>|<span data-ttu-id="2705b-150">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="2705b-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2705b-151">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2705b-151">None</span></span>|<span data-ttu-id="2705b-152">Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="2705b-152">No protection.</span></span>|  
|<span data-ttu-id="2705b-153">Sign</span><span class="sxs-lookup"><span data-stu-id="2705b-153">Sign</span></span>|<span data-ttu-id="2705b-154">I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="2705b-154">Messages are signed.</span></span>|  
|<span data-ttu-id="2705b-155">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="2705b-155">EncryptAndSign</span></span>|<span data-ttu-id="2705b-156">-I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="2705b-156">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2705b-157">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2705b-157">Child Elements</span></span>  
 <span data-ttu-id="2705b-158">Nessuna</span><span class="sxs-lookup"><span data-stu-id="2705b-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2705b-159">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2705b-159">Parent Elements</span></span>  
  
|<span data-ttu-id="2705b-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="2705b-160">Element</span></span>|<span data-ttu-id="2705b-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2705b-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2705b-162">\<security></span><span class="sxs-lookup"><span data-stu-id="2705b-162">\<security></span></span>](security-of-nettcpbinding.md)|<span data-ttu-id="2705b-163">Specifica le funzionalità di sicurezza del [ \<> NetTcpBinding](nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2705b-163">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2705b-164">Note</span><span class="sxs-lookup"><span data-stu-id="2705b-164">Remarks</span></span>  
 <span data-ttu-id="2705b-165">Usare la sicurezza del trasporto garantire l'integrità e la riservatezza del messaggio SOAP, nonché l'esecuzione dell'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="2705b-165">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="2705b-166">Se questa modalità di sicurezza viene selezionata per un'associazione, lo stack di canali viene configurato in modo da usare un trasporto protetto nonché proteggere i messaggi SOAP tramite una sicurezza di trasporto quale Windows (Negotiate) o SSL su TCP.</span><span class="sxs-lookup"><span data-stu-id="2705b-166">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2705b-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2705b-167">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="2705b-168">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="2705b-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2705b-169">Associazioni</span><span class="sxs-lookup"><span data-stu-id="2705b-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2705b-170">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="2705b-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2705b-171">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="2705b-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2705b-172">\<binding></span><span class="sxs-lookup"><span data-stu-id="2705b-172">\<binding></span></span>](../../../misc/binding.md)
