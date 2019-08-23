---
title: <transport> di <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: af5852c3c7850f91686d50294c8846f85574e909
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918629"
---
# <a name="transport-of-basichttpbinding"></a><span data-ttu-id="53262-102">\<> di trasporto \<di BasicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="53262-102">\<transport> of \<basicHttpBinding></span></span>
<span data-ttu-id="53262-103">Definisce proprietà che controllano i parametri di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="53262-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
 <span data-ttu-id="53262-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="53262-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="53262-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="53262-105">\<bindings></span></span>  
<span data-ttu-id="53262-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="53262-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="53262-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="53262-107">\<binding></span></span>  
<span data-ttu-id="53262-108">\<security></span><span class="sxs-lookup"><span data-stu-id="53262-108">\<security></span></span>  
<span data-ttu-id="53262-109">\<> di trasporto</span><span class="sxs-lookup"><span data-stu-id="53262-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53262-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53262-110">Syntax</span></span>  
  
```xml  
<basicHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="String">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53262-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="53262-111">Attributes and Elements</span></span>  
 <span data-ttu-id="53262-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="53262-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53262-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="53262-113">Attributes</span></span>  
  
|<span data-ttu-id="53262-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="53262-114">Attribute</span></span>|<span data-ttu-id="53262-115">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="53262-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53262-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="53262-116">clientCredentialType</span></span>|<span data-ttu-id="53262-117">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client usando l'autenticazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="53262-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="53262-118">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="53262-118">The default is `None`.</span></span> <span data-ttu-id="53262-119">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="53262-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="53262-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="53262-120">proxyCredentialType</span></span>|<span data-ttu-id="53262-121">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client dall'interno di un dominio usando un proxy su HTTP.</span><span class="sxs-lookup"><span data-stu-id="53262-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="53262-122">Questo attributo è applicabile solo quando l'attributo `mode` dell'elemento `security` padre è `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="53262-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="53262-123">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="53262-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="53262-124">realm</span><span class="sxs-lookup"><span data-stu-id="53262-124">realm</span></span>|<span data-ttu-id="53262-125">Stringa che specifica l'area di autenticazione usata dallo schema di autenticazione HTTP per l'autenticazione digest o di base.</span><span class="sxs-lookup"><span data-stu-id="53262-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="53262-126">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="53262-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="53262-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="53262-127">policyEnforcement</span></span>|<span data-ttu-id="53262-128">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="53262-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="53262-129">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="53262-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="53262-130">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="53262-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="53262-131">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="53262-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="53262-132">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="53262-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="53262-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="53262-133">protectionScenario</span></span>|<span data-ttu-id="53262-134">Questa enumerazione specifica lo scenario di protezione applicato dai criteri.</span><span class="sxs-lookup"><span data-stu-id="53262-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="53262-135">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="53262-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="53262-136">Value</span><span class="sxs-lookup"><span data-stu-id="53262-136">Value</span></span>|<span data-ttu-id="53262-137">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="53262-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53262-138">Nessuna</span><span class="sxs-lookup"><span data-stu-id="53262-138">None</span></span>|<span data-ttu-id="53262-139">I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="53262-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="53262-140">Basic</span><span class="sxs-lookup"><span data-stu-id="53262-140">Basic</span></span>|<span data-ttu-id="53262-141">Specifica l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="53262-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="53262-142">Digest</span><span class="sxs-lookup"><span data-stu-id="53262-142">Digest</span></span>|<span data-ttu-id="53262-143">Specifica l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="53262-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="53262-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="53262-144">Ntlm</span></span>|<span data-ttu-id="53262-145">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="53262-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="53262-146">Windows</span><span class="sxs-lookup"><span data-stu-id="53262-146">Windows</span></span>|<span data-ttu-id="53262-147">Specifica l'autenticazione Windows integrata.</span><span class="sxs-lookup"><span data-stu-id="53262-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="53262-148">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="53262-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="53262-149">Valore</span><span class="sxs-lookup"><span data-stu-id="53262-149">Value</span></span>|<span data-ttu-id="53262-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53262-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53262-151">Nessuna</span><span class="sxs-lookup"><span data-stu-id="53262-151">None</span></span>|<span data-ttu-id="53262-152">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="53262-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="53262-153">Basic</span><span class="sxs-lookup"><span data-stu-id="53262-153">Basic</span></span>|<span data-ttu-id="53262-154">Specifica l'autenticazione di base come definito da RFC 2617 – HTTP Authentication: Autenticazione di base e del digest.</span><span class="sxs-lookup"><span data-stu-id="53262-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="53262-155">Digest</span><span class="sxs-lookup"><span data-stu-id="53262-155">Digest</span></span>|<span data-ttu-id="53262-156">Specifica l'autenticazione del digest secondo quanto definito da RFC 2617 – HTTP Authentication: Autenticazione di base e del digest.</span><span class="sxs-lookup"><span data-stu-id="53262-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="53262-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="53262-157">Ntlm</span></span>|<span data-ttu-id="53262-158">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="53262-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="53262-159">Windows</span><span class="sxs-lookup"><span data-stu-id="53262-159">Windows</span></span>|<span data-ttu-id="53262-160">Specifica l'autenticazione Windows integrata.</span><span class="sxs-lookup"><span data-stu-id="53262-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="53262-161">Certificato</span><span class="sxs-lookup"><span data-stu-id="53262-161">Certificate</span></span>|<span data-ttu-id="53262-162">Esegue l'autenticazione client mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="53262-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="53262-163">Questa opzione funziona solo se l'attributo `Mode` dell'elemento `security` padre è impostato su Transport, mentre non funzionerà se viene impostato su TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="53262-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53262-164">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="53262-164">Child Elements</span></span>  
 <span data-ttu-id="53262-165">Nessuna</span><span class="sxs-lookup"><span data-stu-id="53262-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53262-166">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="53262-166">Parent Elements</span></span>  
  
|<span data-ttu-id="53262-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="53262-167">Element</span></span>|<span data-ttu-id="53262-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53262-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53262-169">\<security></span><span class="sxs-lookup"><span data-stu-id="53262-169">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="53262-170">Definisce le funzionalità di sicurezza per il [ \<> BasicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="53262-170">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="53262-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="53262-171">Example</span></span>  
 <span data-ttu-id="53262-172">Nell'esempio seguente è dimostrato l'uso della sicurezza del trasporto SSL con l'associazione di base.</span><span class="sxs-lookup"><span data-stu-id="53262-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="53262-173">Per impostazione predefinita, l'associazione di base supporta la comunicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="53262-173">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
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
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="53262-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53262-174">See also</span></span>

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="53262-175">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="53262-175">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="53262-176">Associazioni</span><span class="sxs-lookup"><span data-stu-id="53262-176">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="53262-177">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="53262-177">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="53262-178">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="53262-178">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="53262-179">\<binding></span><span class="sxs-lookup"><span data-stu-id="53262-179">\<binding></span></span>](../../../misc/binding.md)
