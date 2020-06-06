---
title: <transport> di <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
ms.openlocfilehash: 4ef08ad73a03dea21d27217364a7bacb46a3848e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73735926"
---
# <a name="transport-of-nettcpbinding"></a><span data-ttu-id="f44f4-102">\<transport> di \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="f44f4-102">\<transport> of \<netTcpBinding></span></span>
<span data-ttu-id="f44f4-103">Definisce il tipo di requisiti di sicurezza a livello di messaggio per un endpoint configurato con [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f44f4-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="f44f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f44f4-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f44f4-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f44f4-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f44f4-106">Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f44f4-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f44f4-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f44f4-107">Attributes</span></span>  
  
|<span data-ttu-id="f44f4-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="f44f4-108">Attribute</span></span>|<span data-ttu-id="f44f4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f44f4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f44f4-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f44f4-110">clientCredentialType</span></span>|<span data-ttu-id="f44f4-111">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f44f4-111">Optional.</span></span> <span data-ttu-id="f44f4-112">Specifica il tipo di credenziale da usare se l'autenticazione client viene eseguita usando la sicurezza del trasporto.</span><span class="sxs-lookup"><span data-stu-id="f44f4-112">Specifies the type of credential to be used when performing client authentication using Transport security.</span></span><br /><br /> <span data-ttu-id="f44f4-113">-Il valore predefinito è `Windows` .</span><span class="sxs-lookup"><span data-stu-id="f44f4-113">-   The default value is `Windows`.</span></span><br /><span data-ttu-id="f44f4-114">: Questo attributo è di tipo <xref:System.ServiceModel.TcpClientCredentialType> .</span><span class="sxs-lookup"><span data-stu-id="f44f4-114">-   This attribute is of type <xref:System.ServiceModel.TcpClientCredentialType>.</span></span>|  
|<span data-ttu-id="f44f4-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="f44f4-115">protectionLevel</span></span>|<span data-ttu-id="f44f4-116">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f44f4-116">Optional.</span></span> <span data-ttu-id="f44f4-117">Definisce il livello di sicurezza del trasporto TCP.</span><span class="sxs-lookup"><span data-stu-id="f44f4-117">Defines security at the level of the TCP transport.</span></span> <span data-ttu-id="f44f4-118">La firma dei messaggi riduce il rischio di manomissione del messaggio a opera di terze parti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="f44f4-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="f44f4-119">La crittografia garantisce la privacy a livello dei dati durante il trasporto.</span><span class="sxs-lookup"><span data-stu-id="f44f4-119">Encryption provides data-level privacy during transport.</span></span><br /><br /> <span data-ttu-id="f44f4-120">Il valore predefinito è `EncryptAndSign`.</span><span class="sxs-lookup"><span data-stu-id="f44f4-120">The default value is `EncryptAndSign`.</span></span>|  
|<span data-ttu-id="f44f4-121">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="f44f4-121">sslProtocols</span></span>|<span data-ttu-id="f44f4-122">Valore del flag di enumerazione SslProtocols che specifica gli elementi SslProtocol supportati.</span><span class="sxs-lookup"><span data-stu-id="f44f4-122">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="f44f4-123">Il valore predefinito è TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="f44f4-123">The default is Tls&#124;Tls11&#124;Tls12.</span></span>|  
|<span data-ttu-id="f44f4-124">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="f44f4-124">policyEnforcement</span></span>|<span data-ttu-id="f44f4-125">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="f44f4-125">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="f44f4-126">1. Never: il criterio non viene mai applicato (la protezione estesa è disabilitata).</span><span class="sxs-lookup"><span data-stu-id="f44f4-126">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="f44f4-127">2. WhenSupported: i criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="f44f4-127">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="f44f4-128">3. always: i criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="f44f4-128">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="f44f4-129">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f44f4-129">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="f44f4-130">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f44f4-130">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f44f4-131">Valore</span><span class="sxs-lookup"><span data-stu-id="f44f4-131">Value</span></span>|<span data-ttu-id="f44f4-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f44f4-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f44f4-133">nessuno</span><span class="sxs-lookup"><span data-stu-id="f44f4-133">None</span></span>|<span data-ttu-id="f44f4-134">Il client è anonimo.</span><span class="sxs-lookup"><span data-stu-id="f44f4-134">The client is anonymous.</span></span> <span data-ttu-id="f44f4-135">Richiede un certificato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f44f4-135">This requires a certificate for the service.</span></span>|  
|<span data-ttu-id="f44f4-136">Windows</span><span class="sxs-lookup"><span data-stu-id="f44f4-136">Windows</span></span>|<span data-ttu-id="f44f4-137">Specifica l'autenticazione Windows del client mediante la negoziazione SP (negoziazione Kerberos).</span><span class="sxs-lookup"><span data-stu-id="f44f4-137">Specifies Windows authentication of the client using SP Negotiation (Kerberos negotiation).</span></span>|  
|<span data-ttu-id="f44f4-138">Certificato</span><span class="sxs-lookup"><span data-stu-id="f44f4-138">Certificate</span></span>|<span data-ttu-id="f44f4-139">Il client viene autenticato mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="f44f4-139">The client is authenticated using a certificate.</span></span> <span data-ttu-id="f44f4-140">Viene usata la negoziazione SSL ed è necessario un certificato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="f44f4-140">This uses SSL Negotiation and requires a certificate for the service.</span></span>|  
  
## <a name="protectionlevel-attribute"></a><span data-ttu-id="f44f4-141">Attributo protectionLevel</span><span class="sxs-lookup"><span data-stu-id="f44f4-141">protectionLevel Attribute</span></span>  
  
|<span data-ttu-id="f44f4-142">Valore</span><span class="sxs-lookup"><span data-stu-id="f44f4-142">Value</span></span>|<span data-ttu-id="f44f4-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f44f4-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f44f4-144">nessuno</span><span class="sxs-lookup"><span data-stu-id="f44f4-144">None</span></span>|<span data-ttu-id="f44f4-145">Nessuna protezione.</span><span class="sxs-lookup"><span data-stu-id="f44f4-145">No protection.</span></span>|  
|<span data-ttu-id="f44f4-146">Sign</span><span class="sxs-lookup"><span data-stu-id="f44f4-146">Sign</span></span>|<span data-ttu-id="f44f4-147">I messaggi vengono firmati.</span><span class="sxs-lookup"><span data-stu-id="f44f4-147">Messages are signed.</span></span>|  
|<span data-ttu-id="f44f4-148">EncryptAndSign</span><span class="sxs-lookup"><span data-stu-id="f44f4-148">EncryptAndSign</span></span>|<span data-ttu-id="f44f4-149">-I messaggi vengono crittografati e firmati.</span><span class="sxs-lookup"><span data-stu-id="f44f4-149">-   Messages are encrypted and signed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f44f4-150">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f44f4-150">Child Elements</span></span>  
 <span data-ttu-id="f44f4-151">nessuno</span><span class="sxs-lookup"><span data-stu-id="f44f4-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f44f4-152">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f44f4-152">Parent Elements</span></span>  
  
|<span data-ttu-id="f44f4-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="f44f4-153">Element</span></span>|<span data-ttu-id="f44f4-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f44f4-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="f44f4-155">Specifica le funzionalità di sicurezza di [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f44f4-155">Specifies the security capabilities of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f44f4-156">Commenti</span><span class="sxs-lookup"><span data-stu-id="f44f4-156">Remarks</span></span>  
 <span data-ttu-id="f44f4-157">Usare la sicurezza del trasporto garantire l'integrità e la riservatezza del messaggio SOAP, nonché l'esecuzione dell'autenticazione reciproca.</span><span class="sxs-lookup"><span data-stu-id="f44f4-157">Use Transport security for integrity and confidentiality of the SOAP message and for mutual authentication.</span></span> <span data-ttu-id="f44f4-158">Se questa modalità di sicurezza viene selezionata per un'associazione, lo stack di canali viene configurato in modo da usare un trasporto protetto nonché proteggere i messaggi SOAP tramite una sicurezza di trasporto quale Windows (Negotiate) o SSL su TCP.</span><span class="sxs-lookup"><span data-stu-id="f44f4-158">If this security mode is selected on a binding, the channel stack is configured using a secure transport and the SOAP messages are secured using transport security such as Windows (Negotiate) or SSL over TCP.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f44f4-159">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f44f4-159">See also</span></span>

- <xref:System.ServiceModel.TcpTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="f44f4-160">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="f44f4-160">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f44f4-161">Binding</span><span class="sxs-lookup"><span data-stu-id="f44f4-161">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f44f4-162">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="f44f4-162">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f44f4-163">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f44f4-163">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
