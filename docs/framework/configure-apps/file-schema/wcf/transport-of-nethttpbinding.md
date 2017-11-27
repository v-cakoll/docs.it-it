---
title: '&lt;transport&gt; di &lt;netHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 67bacedb9a2e46903b97ea0747880bbb1af24a68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltnethttpbindinggt"></a><span data-ttu-id="8a4ba-102">&lt;transport&gt; di &lt;netHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="8a4ba-102">&lt;transport&gt; of &lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="8a4ba-103">Definisce proprietà che controllano i parametri di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
<span data-ttu-id="8a4ba-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8a4ba-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8a4ba-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="8a4ba-105">\<bindings></span></span>  
<span data-ttu-id="8a4ba-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="8a4ba-106">\<netHttpBinding></span></span>  
<span data-ttu-id="8a4ba-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="8a4ba-107">\<binding></span></span>  
<span data-ttu-id="8a4ba-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="8a4ba-108">\<security></span></span>  
<span data-ttu-id="8a4ba-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="8a4ba-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a4ba-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a4ba-110">Syntax</span></span>  
  
```xml
<netHttpBinding>  
  <binding>  
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string">  
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"  
                                  protectionScenario="TransportSelected|TrustedProxy">  
          <customServiceNames></customServiceNames>  
        </extendedProtectionPolicy>  
      </transport>  
    </security>  
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a4ba-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8a4ba-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8a4ba-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a4ba-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="8a4ba-113">Attributes</span></span>  
  
|<span data-ttu-id="8a4ba-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="8a4ba-114">Attribute</span></span>|<span data-ttu-id="8a4ba-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a4ba-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a4ba-116">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8a4ba-116">clientCredentialType</span></span>|<span data-ttu-id="8a4ba-117">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client mediante l'autenticazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-117">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="8a4ba-118">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-118">The default is `None`.</span></span> <span data-ttu-id="8a4ba-119">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="8a4ba-120">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="8a4ba-120">proxyCredentialType</span></span>|<span data-ttu-id="8a4ba-121">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client all'interno di un dominio tramite un proxy su HTTP.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-121">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="8a4ba-122">Questo attributo è applicabile solo quando l'attributo `mode` dell'elemento `security` padre è `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-122">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="8a4ba-123">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-123">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="8a4ba-124">realm</span><span class="sxs-lookup"><span data-stu-id="8a4ba-124">realm</span></span>|<span data-ttu-id="8a4ba-125">Stringa che specifica l'area di autenticazione usata dallo schema di autenticazione HTTP per l'autenticazione digest o di base.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-125">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="8a4ba-126">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-126">The default is an empty string.</span></span>|  
|<span data-ttu-id="8a4ba-127">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="8a4ba-127">policyEnforcement</span></span>|<span data-ttu-id="8a4ba-128">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-128">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="8a4ba-129">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-129">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="8a4ba-130">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-130">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="8a4ba-131">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-131">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="8a4ba-132">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-132">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="8a4ba-133">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="8a4ba-133">protectionScenario</span></span>|<span data-ttu-id="8a4ba-134">Questa enumerazione specifica lo scenario di protezione applicato dai criteri.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-134">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="8a4ba-135">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="8a4ba-135">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8a4ba-136">Valore</span><span class="sxs-lookup"><span data-stu-id="8a4ba-136">Value</span></span>|<span data-ttu-id="8a4ba-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a4ba-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a4ba-138">None</span><span class="sxs-lookup"><span data-stu-id="8a4ba-138">None</span></span>|<span data-ttu-id="8a4ba-139">I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-139">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8a4ba-140">Di base</span><span class="sxs-lookup"><span data-stu-id="8a4ba-140">Basic</span></span>|<span data-ttu-id="8a4ba-141">Specifica l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-141">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="8a4ba-142">Digest</span><span class="sxs-lookup"><span data-stu-id="8a4ba-142">Digest</span></span>|<span data-ttu-id="8a4ba-143">Specifica l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-143">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="8a4ba-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8a4ba-144">Ntlm</span></span>|<span data-ttu-id="8a4ba-145">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-145">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8a4ba-146">Windows</span><span class="sxs-lookup"><span data-stu-id="8a4ba-146">Windows</span></span>|<span data-ttu-id="8a4ba-147">Specifica l'autenticazione Windows integrata.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-147">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="8a4ba-148">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="8a4ba-148">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="8a4ba-149">Valore</span><span class="sxs-lookup"><span data-stu-id="8a4ba-149">Value</span></span>|<span data-ttu-id="8a4ba-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a4ba-150">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a4ba-151">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8a4ba-151">None</span></span>|<span data-ttu-id="8a4ba-152">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-152">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="8a4ba-153">Basic</span><span class="sxs-lookup"><span data-stu-id="8a4ba-153">Basic</span></span>|<span data-ttu-id="8a4ba-154">Specifica l'autenticazione di base come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-154">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8a4ba-155">Digest</span><span class="sxs-lookup"><span data-stu-id="8a4ba-155">Digest</span></span>|<span data-ttu-id="8a4ba-156">Specifica l'autenticazione digest come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-156">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="8a4ba-157">Ntlm</span><span class="sxs-lookup"><span data-stu-id="8a4ba-157">Ntlm</span></span>|<span data-ttu-id="8a4ba-158">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-158">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="8a4ba-159">Windows</span><span class="sxs-lookup"><span data-stu-id="8a4ba-159">Windows</span></span>|<span data-ttu-id="8a4ba-160">Specifica l'autenticazione Windows integrata.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-160">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="8a4ba-161">Certificato</span><span class="sxs-lookup"><span data-stu-id="8a4ba-161">Certificate</span></span>|<span data-ttu-id="8a4ba-162">Esegue l'autenticazione client mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-162">Performs client authentication using a certificate.</span></span> <span data-ttu-id="8a4ba-163">Questa opzione funziona solo se l'attributo `Mode` dell'elemento `security` padre è impostato su Transport, mentre non funzionerà se viene impostato su TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-163">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a4ba-164">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8a4ba-164">Child Elements</span></span>  
 <span data-ttu-id="8a4ba-165">None</span><span class="sxs-lookup"><span data-stu-id="8a4ba-165">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a4ba-166">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8a4ba-166">Parent Elements</span></span>  
  
|<span data-ttu-id="8a4ba-167">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a4ba-167">Element</span></span>|<span data-ttu-id="8a4ba-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a4ba-168">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a4ba-169">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="8a4ba-169">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nethttpbinding.md)|<span data-ttu-id="8a4ba-170">Definisce le funzionalità di sicurezza per il [ \<netHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="8a4ba-170">Defines the security capabilities for the [\<netHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a4ba-171">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a4ba-171">Example</span></span>  
 <span data-ttu-id="8a4ba-172">Nell'esempio seguente è dimostrato l'uso della sicurezza del trasporto SSL con l'associazione di base.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-172">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="8a4ba-173">Per impostazione predefinita, l'associazione di base supporta la comunicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-173">By default, the basic binding supports HTTP communication.</span></span>  
  
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
      <!-- Configure basicHttpBinding with Transport security -- >  
      <!-- mode and clientCredentialType set to None.-->  
      <binding name="Binding1">  
        <security mode="Transport">  
          <transport clientCredentialType="None"  
                     proxyCredentialType="None">  
            <extendedProtectionPolicy policyEnforcement="WhenSupported"  
                                      protectionScenario="TransportSelected">  
              <customServiceNames></customServiceNames>  
            </extendedProtectionPolicy>
          </transport> 
        </security>  
      </binding>  
    </netHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a4ba-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a4ba-174">See Also</span></span>  
 <span data-ttu-id="8a4ba-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span><span class="sxs-lookup"><span data-stu-id="8a4ba-175"><xref:System.ServiceModel.BasicHttpSecurityMode.Transport> <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement></span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [<span data-ttu-id="8a4ba-176">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="8a4ba-176">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="8a4ba-177">Associazioni</span><span class="sxs-lookup"><span data-stu-id="8a4ba-177">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8a4ba-178">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="8a4ba-178">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="8a4ba-179">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8a4ba-179">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="8a4ba-180">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="8a4ba-180">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
