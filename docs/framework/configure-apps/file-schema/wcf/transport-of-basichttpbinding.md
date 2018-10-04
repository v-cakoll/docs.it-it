---
title: '&lt;transport&gt; di &lt;basicHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: f4e37281539106fef93dc4ab566d94d781c39d29
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48777721"
---
# <a name="lttransportgt-of-ltbasichttpbindinggt"></a><span data-ttu-id="1063f-102">&lt;transport&gt; di &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1063f-102">&lt;transport&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="1063f-103">Definisce proprietà che controllano i parametri di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="1063f-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
 <span data-ttu-id="1063f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1063f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1063f-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="1063f-105">\<bindings></span></span>  
<span data-ttu-id="1063f-106">\<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1063f-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="1063f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1063f-107">\<binding></span></span>  
<span data-ttu-id="1063f-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1063f-108">\<security></span></span>  
<span data-ttu-id="1063f-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="1063f-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1063f-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1063f-110">Syntax</span></span>  
  
```xml  
<basicHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1063f-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1063f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1063f-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1063f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1063f-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="1063f-113">Attributes</span></span>  
  
|<span data-ttu-id="1063f-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="1063f-114">Attribute</span></span>|<span data-ttu-id="1063f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1063f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1063f-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="1063f-116">clientCredentialType</span></span>|<span data-ttu-id="1063f-117">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client mediante l'autenticazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="1063f-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="1063f-118">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="1063f-118">The default is `None`.</span></span> <span data-ttu-id="1063f-119">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="1063f-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="1063f-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="1063f-120">proxyCredentialType</span></span>|<span data-ttu-id="1063f-121">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione dal client all'interno di un dominio tramite un proxy su HTTP.</span><span class="sxs-lookup"><span data-stu-id="1063f-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="1063f-122">Questo attributo è applicabile solo quando l'attributo `mode` dell'elemento `security` padre è `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="1063f-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="1063f-123">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="1063f-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="1063f-124">realm</span><span class="sxs-lookup"><span data-stu-id="1063f-124">realm</span></span>|<span data-ttu-id="1063f-125">Stringa che specifica l'area di autenticazione usata dallo schema di autenticazione HTTP per l'autenticazione digest o di base.</span><span class="sxs-lookup"><span data-stu-id="1063f-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="1063f-126">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="1063f-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="1063f-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="1063f-127">policyEnforcement</span></span>|<span data-ttu-id="1063f-128">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="1063f-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="1063f-129">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="1063f-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="1063f-130">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="1063f-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="1063f-131">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="1063f-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="1063f-132">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1063f-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="1063f-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="1063f-133">protectionScenario</span></span>|<span data-ttu-id="1063f-134">Questa enumerazione specifica lo scenario di protezione applicato dai criteri.</span><span class="sxs-lookup"><span data-stu-id="1063f-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="1063f-135">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="1063f-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="1063f-136">Valore</span><span class="sxs-lookup"><span data-stu-id="1063f-136">Value</span></span>|<span data-ttu-id="1063f-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1063f-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1063f-138">None</span><span class="sxs-lookup"><span data-stu-id="1063f-138">None</span></span>|<span data-ttu-id="1063f-139">I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="1063f-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="1063f-140">Di base</span><span class="sxs-lookup"><span data-stu-id="1063f-140">Basic</span></span>|<span data-ttu-id="1063f-141">Specifica l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="1063f-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="1063f-142">Digest</span><span class="sxs-lookup"><span data-stu-id="1063f-142">Digest</span></span>|<span data-ttu-id="1063f-143">Specifica l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="1063f-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="1063f-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="1063f-144">Ntlm</span></span>|<span data-ttu-id="1063f-145">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="1063f-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="1063f-146">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="1063f-146">Windows</span></span>|<span data-ttu-id="1063f-147">Specifica l'autenticazione Windows integrata.</span><span class="sxs-lookup"><span data-stu-id="1063f-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="1063f-148">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="1063f-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="1063f-149">Valore</span><span class="sxs-lookup"><span data-stu-id="1063f-149">Value</span></span>|<span data-ttu-id="1063f-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1063f-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1063f-151">nessuno</span><span class="sxs-lookup"><span data-stu-id="1063f-151">None</span></span>|<span data-ttu-id="1063f-152">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="1063f-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="1063f-153">Basic</span><span class="sxs-lookup"><span data-stu-id="1063f-153">Basic</span></span>|<span data-ttu-id="1063f-154">Specifica l'autenticazione di base come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="1063f-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="1063f-155">Digest</span><span class="sxs-lookup"><span data-stu-id="1063f-155">Digest</span></span>|<span data-ttu-id="1063f-156">Specifica l'autenticazione digest come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="1063f-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="1063f-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="1063f-157">Ntlm</span></span>|<span data-ttu-id="1063f-158">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="1063f-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="1063f-159">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="1063f-159">Windows</span></span>|<span data-ttu-id="1063f-160">Specifica l'autenticazione Windows integrata.</span><span class="sxs-lookup"><span data-stu-id="1063f-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="1063f-161">Certificato</span><span class="sxs-lookup"><span data-stu-id="1063f-161">Certificate</span></span>|<span data-ttu-id="1063f-162">Esegue l'autenticazione client mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="1063f-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="1063f-163">Questa opzione funziona solo se l'attributo `Mode` dell'elemento `security` padre è impostato su Transport, mentre non funzionerà se viene impostato su TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="1063f-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1063f-164">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1063f-164">Child Elements</span></span>  
 <span data-ttu-id="1063f-165">nessuno</span><span class="sxs-lookup"><span data-stu-id="1063f-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1063f-166">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1063f-166">Parent Elements</span></span>  
  
|<span data-ttu-id="1063f-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="1063f-167">Element</span></span>|<span data-ttu-id="1063f-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1063f-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1063f-169">\<security></span><span class="sxs-lookup"><span data-stu-id="1063f-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="1063f-170">Definisce le funzionalità di sicurezza per il [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1063f-170">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1063f-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="1063f-171">Example</span></span>  
 <span data-ttu-id="1063f-172">Nell'esempio seguente è dimostrato l'uso della sicurezza del trasporto SSL con l'associazione di base.</span><span class="sxs-lookup"><span data-stu-id="1063f-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="1063f-173">Per impostazione predefinita, l'associazione di base supporta la comunicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="1063f-173">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>  
   <services>  
      <service   
          type="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
         <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
   </services>  
    <bindings>  
        <basicHttpBinding>  
        <!-- Configure basicHttpBinding with Transport security -- >  
        <!-- mode and clientCredentialType set to None.-->  
           <binding name="Binding1">  
               <security mode="Transport">  
                   <transport clientCredentialType="None"  
                              proxyCredentialType="None">  
                       <extendedProtectionPolicy  
                          policyEnforcement="WhenSupported"  
                          protectionScenario="TransportSelected">  
                    <customServiceNames></customServiceNames>  
                       </extendedProtectionPolicy>  
               </security>  
           </binding>  
        </basicHttpBinding>  
    </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1063f-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1063f-174">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [<span data-ttu-id="1063f-175">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="1063f-175">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1063f-176">Associazioni</span><span class="sxs-lookup"><span data-stu-id="1063f-176">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1063f-177">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="1063f-177">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1063f-178">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="1063f-178">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="1063f-179">\<binding></span><span class="sxs-lookup"><span data-stu-id="1063f-179">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
