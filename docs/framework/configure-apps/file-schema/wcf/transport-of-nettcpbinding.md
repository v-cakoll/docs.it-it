---
title: '&lt;transport&gt; di &lt;netTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 7372b94bde8325ec00116ee7022739f1b17a1ac9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555492"
---
# <a name="lttransportgt-of-ltnettcpbindinggt"></a><span data-ttu-id="f081a-102">&lt;transport&gt; di &lt;netTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="f081a-102">&lt;transport&gt; of &lt;netTcpBinding&gt;</span></span>
<span data-ttu-id="f081a-103">Definisce il tipo di requisiti di sicurezza a livello di messaggio per un endpoint configurato con il [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f081a-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>  
  
 <span data-ttu-id="f081a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f081a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f081a-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="f081a-105">\<bindings></span></span>  
<span data-ttu-id="f081a-106">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="f081a-106">\<netTcpBinding></span></span>  
<span data-ttu-id="f081a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f081a-107">\<binding></span></span>  
<span data-ttu-id="f081a-108">\<security></span><span class="sxs-lookup"><span data-stu-id="f081a-108">\<security></span></span>  
<span data-ttu-id="f081a-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="f081a-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f081a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f081a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f081a-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f081a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f081a-112">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f081a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f081a-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="f081a-113">Attributes</span></span>  
  
|<span data-ttu-id="f081a-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="f081a-114">Attribute</span></span>|<span data-ttu-id="f081a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f081a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f081a-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f081a-116">clientCredentialType</span></span>|<span data-ttu-id="f081a-117">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f081a-117">Optional.</span></span> <span data-ttu-id="f081a-118">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="f081a-118">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="f081a-119">-Il valore predefinito è `Windows`.</span><span class="sxs-lookup"><span data-stu-id="f081a-119">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="f081a-120">-L'attributo è di tipo <xref:System.ServiceModel.TcpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f081a-120">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="f081a-121">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="f081a-121">protectionLevel</span></span>|<span data-ttu-id="f081a-122">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="f081a-122">Optional.</span></span> <span data-ttu-id="f081a-123">Definisce il livello di sicurezza del trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="f081a-123">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="f081a-124">La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="f081a-124">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="f081a-125">La crittografia fornisce riservatezza a livello di dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="f081a-125">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="f081a-126">Il valore predefinito è `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="f081a-126">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="f081a-127">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="f081a-127">sslProtocols</span></span>|<span data-ttu-id="f081a-128">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="f081a-128">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="f081a-129">Il valore predefinito è Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="f081a-129">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="f081a-130">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="f081a-130">policyEnforcement</span></span>|<span data-ttu-id="f081a-131">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="f081a-131">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="f081a-132">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f081a-132">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="f081a-133">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="f081a-133">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="f081a-134">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="f081a-134">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="f081a-135">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f081a-135">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="f081a-136">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f081a-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f081a-137">Valore</span><span class="sxs-lookup"><span data-stu-id="f081a-137">Value</span></span>|<span data-ttu-id="f081a-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f081a-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f081a-139">None</span><span class="sxs-lookup"><span data-stu-id="f081a-139">None</span></span>|<span data-ttu-id="f081a-140">Il client è anonimo.</span><span class="sxs-lookup"><span data-stu-id="f081a-140">The client is anonymous.</span></span> <span data-ttu-id="f081a-141">Richiede un certificato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f081a-141">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="f081a-142">Windows</span><span class="sxs-lookup"><span data-stu-id="f081a-142">Windows</span></span>|<span data-ttu-id="f081a-143">Specifica l'autenticazione Windows del client mediante la negoziazione SP (negoziazione Kerberos).</span><span class="sxs-lookup"><span data-stu-id="f081a-143">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="f081a-144">Certificato</span><span class="sxs-lookup"><span data-stu-id="f081a-144">Certificate</span></span>|<span data-ttu-id="f081a-145">Il client viene autenticato mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="f081a-145">The client is authenticated using a certificate.</span></span> <span data-ttu-id="f081a-146">Viene usata la negoziazione SSL ed è necessario un certificato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f081a-146">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="f081a-147">Attributo protectionLevel</span><span class="sxs-lookup"><span data-stu-id="f081a-147">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="f081a-148">Valore</span><span class="sxs-lookup"><span data-stu-id="f081a-148">Value</span></span>|<span data-ttu-id="f081a-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f081a-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f081a-150">None</span><span class="sxs-lookup"><span data-stu-id="f081a-150">None</span></span>|<span data-ttu-id="f081a-151">Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="f081a-151">No protection.</span></span>|  
|<span data-ttu-id="f081a-152">Sign</span><span class="sxs-lookup"><span data-stu-id="f081a-152">Sign</span></span>|<span data-ttu-id="f081a-153">I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="f081a-153">Messages are signed.</span></span>|  
|<span data-ttu-id="f081a-154">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="f081a-154">EncryptAndSign</span></span>|<span data-ttu-id="f081a-155">-I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="f081a-155">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f081a-156">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f081a-156">Child Elements</span></span>  
 <span data-ttu-id="f081a-157">nessuno</span><span class="sxs-lookup"><span data-stu-id="f081a-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f081a-158">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f081a-158">Parent Elements</span></span>  
  
|<span data-ttu-id="f081a-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="f081a-159">Element</span></span>|<span data-ttu-id="f081a-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f081a-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f081a-161">\<security></span><span class="sxs-lookup"><span data-stu-id="f081a-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="f081a-162">Specifica le funzionalità di sicurezza del [ \<netTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f081a-162">Specifies the security capabilities of the [\<netTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f081a-163">Note</span><span class="sxs-lookup"><span data-stu-id="f081a-163">Remarks</span></span>  
 <span data-ttu-id="f081a-164">Usare la sicurezza del trasporto garantire l'integrità e la riservatezza del messaggio SOAP, nonché l'esecuzione dell'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="f081a-164">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="f081a-165">Se questa modalità di sicurezza viene selezionata per un'associazione, lo stack di canali viene configurato in modo da usare un trasporto protetto nonché proteggere i messaggi SOAP tramite una sicurezza di trasporto quale Windows (Negotiate) o SSL su TCP.</span><span class="sxs-lookup"><span data-stu-id="f081a-165">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f081a-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f081a-166">See also</span></span>
- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="f081a-167">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="f081a-167">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f081a-168">Associazioni</span><span class="sxs-lookup"><span data-stu-id="f081a-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f081a-169">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="f081a-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f081a-170">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f081a-170">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f081a-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="f081a-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
