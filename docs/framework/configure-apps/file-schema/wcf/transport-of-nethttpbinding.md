---
title: <transport> di <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: b975015a9c9a0af53117900c45d917ce1c1a53e9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732819"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="155ea-102">\<> di trasporto di \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="155ea-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="155ea-103">Definisce proprietà che controllano i parametri di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="155ea-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="155ea-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="155ea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="155ea-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="155ea-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="155ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="155ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="155ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**NetHttpBinding**](nethttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="155ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="155ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="155ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="155ea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**sicurezza**](security-of-nethttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="155ea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="155ea-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport** ></span><span class="sxs-lookup"><span data-stu-id="155ea-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="155ea-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="155ea-111">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="155ea-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="155ea-112">Attributes and Elements</span></span>  
 <span data-ttu-id="155ea-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="155ea-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="155ea-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="155ea-114">Attributes</span></span>  
  
|<span data-ttu-id="155ea-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="155ea-115">Attribute</span></span>|<span data-ttu-id="155ea-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="155ea-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="155ea-117">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="155ea-117">clientCredentialType</span></span>|<span data-ttu-id="155ea-118">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client usando l'autenticazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="155ea-118">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="155ea-119">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="155ea-119">The default is `None`.</span></span> <span data-ttu-id="155ea-120">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="155ea-120">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="155ea-121">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="155ea-121">proxyCredentialType</span></span>|<span data-ttu-id="155ea-122">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client dall'interno di un dominio usando un proxy su HTTP.</span><span class="sxs-lookup"><span data-stu-id="155ea-122">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="155ea-123">Questo attributo è applicabile solo quando l'attributo `mode` dell'elemento `security` padre è `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="155ea-123">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="155ea-124">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="155ea-124">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="155ea-125">realm</span><span class="sxs-lookup"><span data-stu-id="155ea-125">realm</span></span>|<span data-ttu-id="155ea-126">Stringa che specifica l'area di autenticazione usata dallo schema di autenticazione HTTP per l'autenticazione digest o di base.</span><span class="sxs-lookup"><span data-stu-id="155ea-126">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="155ea-127">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="155ea-127">The default is an empty string.</span></span>|  
|<span data-ttu-id="155ea-128">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="155ea-128">policyEnforcement</span></span>|<span data-ttu-id="155ea-129">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="155ea-129">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="155ea-130">1. Never: il criterio non viene mai applicato (la protezione estesa è disabilitata).</span><span class="sxs-lookup"><span data-stu-id="155ea-130">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="155ea-131">2. WhenSupported: i criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="155ea-131">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="155ea-132">3. always: i criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="155ea-132">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="155ea-133">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="155ea-133">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="155ea-134">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="155ea-134">protectionScenario</span></span>|<span data-ttu-id="155ea-135">Questa enumerazione specifica lo scenario di protezione applicato dai criteri.</span><span class="sxs-lookup"><span data-stu-id="155ea-135">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="155ea-136">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="155ea-136">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="155ea-137">Value</span><span class="sxs-lookup"><span data-stu-id="155ea-137">Value</span></span>|<span data-ttu-id="155ea-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="155ea-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="155ea-139">Nessuno</span><span class="sxs-lookup"><span data-stu-id="155ea-139">None</span></span>|<span data-ttu-id="155ea-140">I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="155ea-140">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="155ea-141">Basic</span><span class="sxs-lookup"><span data-stu-id="155ea-141">Basic</span></span>|<span data-ttu-id="155ea-142">Specifica l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="155ea-142">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="155ea-143">Digest</span><span class="sxs-lookup"><span data-stu-id="155ea-143">Digest</span></span>|<span data-ttu-id="155ea-144">Specifica l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="155ea-144">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="155ea-145">Ntlm</span><span class="sxs-lookup"><span data-stu-id="155ea-145">Ntlm</span></span>|<span data-ttu-id="155ea-146">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="155ea-146">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="155ea-147">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="155ea-147">Windows</span></span>|<span data-ttu-id="155ea-148">Specifica l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="155ea-148">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="155ea-149">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="155ea-149">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="155ea-150">Value</span><span class="sxs-lookup"><span data-stu-id="155ea-150">Value</span></span>|<span data-ttu-id="155ea-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="155ea-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="155ea-152">Nessuno</span><span class="sxs-lookup"><span data-stu-id="155ea-152">None</span></span>|<span data-ttu-id="155ea-153">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="155ea-153">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="155ea-154">Basic</span><span class="sxs-lookup"><span data-stu-id="155ea-154">Basic</span></span>|<span data-ttu-id="155ea-155">Specifica l'autenticazione di base come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="155ea-155">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="155ea-156">Digest</span><span class="sxs-lookup"><span data-stu-id="155ea-156">Digest</span></span>|<span data-ttu-id="155ea-157">Specifica l'autenticazione digest come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="155ea-157">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="155ea-158">Ntlm</span><span class="sxs-lookup"><span data-stu-id="155ea-158">Ntlm</span></span>|<span data-ttu-id="155ea-159">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="155ea-159">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="155ea-160">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="155ea-160">Windows</span></span>|<span data-ttu-id="155ea-161">Specifica l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="155ea-161">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="155ea-162">Certificato</span><span class="sxs-lookup"><span data-stu-id="155ea-162">Certificate</span></span>|<span data-ttu-id="155ea-163">Esegue l'autenticazione client mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="155ea-163">Performs client authentication using a certificate.</span></span> <span data-ttu-id="155ea-164">Questa opzione funziona solo se l'attributo `Mode` dell'elemento `security` padre è impostato su Transport, mentre non funzionerà se viene impostato su TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="155ea-164">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="155ea-165">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="155ea-165">Child Elements</span></span>  
 <span data-ttu-id="155ea-166">Nessuno</span><span class="sxs-lookup"><span data-stu-id="155ea-166">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="155ea-167">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="155ea-167">Parent Elements</span></span>  
  
|<span data-ttu-id="155ea-168">Elemento</span><span class="sxs-lookup"><span data-stu-id="155ea-168">Element</span></span>|<span data-ttu-id="155ea-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="155ea-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="155ea-170">\<security ></span><span class="sxs-lookup"><span data-stu-id="155ea-170">\<security></span></span>](security-of-nethttpbinding.md)|<span data-ttu-id="155ea-171">Definisce le funzionalità di sicurezza per il [\<> NetHttpBinding](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="155ea-171">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="155ea-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="155ea-172">Example</span></span>  
 <span data-ttu-id="155ea-173">Nell'esempio seguente è dimostrato l'uso della sicurezza del trasporto SSL con l'associazione di base.</span><span class="sxs-lookup"><span data-stu-id="155ea-173">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="155ea-174">Per impostazione predefinita, l'associazione di base supporta la comunicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="155ea-174">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="155ea-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="155ea-175">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="155ea-176">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="155ea-176">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="155ea-177">Associazioni</span><span class="sxs-lookup"><span data-stu-id="155ea-177">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="155ea-178">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="155ea-178">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="155ea-179">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="155ea-179">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="155ea-180">\<binding ></span><span class="sxs-lookup"><span data-stu-id="155ea-180">\<binding></span></span>](bindings.md)
