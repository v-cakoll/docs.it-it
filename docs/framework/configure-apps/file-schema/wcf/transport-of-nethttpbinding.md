---
title: <transport> di <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: b975015a9c9a0af53117900c45d917ce1c1a53e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732819"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="6c03a-102">\<transport> di \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="6c03a-102">\<transport> of \<netHttpBinding></span></span>
<span data-ttu-id="6c03a-103">Definisce proprietà che controllano i parametri di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="6c03a-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="6c03a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c03a-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c03a-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6c03a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6c03a-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6c03a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c03a-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="6c03a-107">Attributes</span></span>  
  
|<span data-ttu-id="6c03a-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="6c03a-108">Attribute</span></span>|<span data-ttu-id="6c03a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c03a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c03a-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="6c03a-110">clientCredentialType</span></span>|<span data-ttu-id="6c03a-111">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client usando l'autenticazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="6c03a-111">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="6c03a-112">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="6c03a-112">The default is `None`.</span></span> <span data-ttu-id="6c03a-113">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6c03a-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="6c03a-114">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="6c03a-114">proxyCredentialType</span></span>|<span data-ttu-id="6c03a-115">-Specifica il tipo di credenziale da usare quando si esegue l'autenticazione client dall'interno di un dominio usando un proxy su HTTP.</span><span class="sxs-lookup"><span data-stu-id="6c03a-115">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="6c03a-116">Questo attributo è applicabile solo quando l'attributo `mode` dell'elemento `security` padre è `Transport` o `TransportCredentialsOnly`.</span><span class="sxs-lookup"><span data-stu-id="6c03a-116">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="6c03a-117">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="6c03a-117">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="6c03a-118">realm</span><span class="sxs-lookup"><span data-stu-id="6c03a-118">realm</span></span>|<span data-ttu-id="6c03a-119">Stringa che specifica l'area di autenticazione usata dallo schema di autenticazione HTTP per l'autenticazione digest o di base.</span><span class="sxs-lookup"><span data-stu-id="6c03a-119">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="6c03a-120">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="6c03a-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="6c03a-121">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="6c03a-121">policyEnforcement</span></span>|<span data-ttu-id="6c03a-122">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="6c03a-122">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="6c03a-123">1. Never: il criterio non viene mai applicato (la protezione estesa è disabilitata).</span><span class="sxs-lookup"><span data-stu-id="6c03a-123">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="6c03a-124">2. WhenSupported: i criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="6c03a-124">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="6c03a-125">3. always: i criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="6c03a-125">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="6c03a-126">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="6c03a-126">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="6c03a-127">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="6c03a-127">protectionScenario</span></span>|<span data-ttu-id="6c03a-128">Questa enumerazione specifica lo scenario di protezione applicato dai criteri.</span><span class="sxs-lookup"><span data-stu-id="6c03a-128">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="6c03a-129">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="6c03a-129">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6c03a-130">Valore</span><span class="sxs-lookup"><span data-stu-id="6c03a-130">Value</span></span>|<span data-ttu-id="6c03a-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c03a-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6c03a-132">nessuno</span><span class="sxs-lookup"><span data-stu-id="6c03a-132">None</span></span>|<span data-ttu-id="6c03a-133">I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="6c03a-133">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="6c03a-134">Basic</span><span class="sxs-lookup"><span data-stu-id="6c03a-134">Basic</span></span>|<span data-ttu-id="6c03a-135">Specifica l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="6c03a-135">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="6c03a-136">Digest</span><span class="sxs-lookup"><span data-stu-id="6c03a-136">Digest</span></span>|<span data-ttu-id="6c03a-137">Specifica l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="6c03a-137">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="6c03a-138">NTLM</span><span class="sxs-lookup"><span data-stu-id="6c03a-138">Ntlm</span></span>|<span data-ttu-id="6c03a-139">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="6c03a-139">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="6c03a-140">Windows</span><span class="sxs-lookup"><span data-stu-id="6c03a-140">Windows</span></span>|<span data-ttu-id="6c03a-141">Specifica l'autenticazione Windows integrata.</span><span class="sxs-lookup"><span data-stu-id="6c03a-141">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="6c03a-142">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="6c03a-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="6c03a-143">Valore</span><span class="sxs-lookup"><span data-stu-id="6c03a-143">Value</span></span>|<span data-ttu-id="6c03a-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c03a-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6c03a-145">nessuno</span><span class="sxs-lookup"><span data-stu-id="6c03a-145">None</span></span>|<span data-ttu-id="6c03a-146">-I messaggi non vengono protetti durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="6c03a-146">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="6c03a-147">Basic</span><span class="sxs-lookup"><span data-stu-id="6c03a-147">Basic</span></span>|<span data-ttu-id="6c03a-148">Specifica l'autenticazione di base come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="6c03a-148">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="6c03a-149">Digest</span><span class="sxs-lookup"><span data-stu-id="6c03a-149">Digest</span></span>|<span data-ttu-id="6c03a-150">Specifica l'autenticazione digest come definita da RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="6c03a-150">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="6c03a-151">NTLM</span><span class="sxs-lookup"><span data-stu-id="6c03a-151">Ntlm</span></span>|<span data-ttu-id="6c03a-152">Specifica l'autenticazione NTLM quando possibile e se l'autenticazione di Windows non riesce.</span><span class="sxs-lookup"><span data-stu-id="6c03a-152">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="6c03a-153">Windows</span><span class="sxs-lookup"><span data-stu-id="6c03a-153">Windows</span></span>|<span data-ttu-id="6c03a-154">Specifica l'autenticazione Windows integrata.</span><span class="sxs-lookup"><span data-stu-id="6c03a-154">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="6c03a-155">Certificato</span><span class="sxs-lookup"><span data-stu-id="6c03a-155">Certificate</span></span>|<span data-ttu-id="6c03a-156">Esegue l'autenticazione client mediante un certificato.</span><span class="sxs-lookup"><span data-stu-id="6c03a-156">Performs client authentication using a certificate.</span></span> <span data-ttu-id="6c03a-157">Questa opzione funziona solo se l'attributo `Mode` dell'elemento `security` padre è impostato su Transport, mentre non funzionerà se viene impostato su TransportCredentialOnly.</span><span class="sxs-lookup"><span data-stu-id="6c03a-157">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c03a-158">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6c03a-158">Child Elements</span></span>  
 <span data-ttu-id="6c03a-159">nessuno</span><span class="sxs-lookup"><span data-stu-id="6c03a-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c03a-160">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6c03a-160">Parent Elements</span></span>  
  
|<span data-ttu-id="6c03a-161">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c03a-161">Element</span></span>|<span data-ttu-id="6c03a-162">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c03a-162">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="6c03a-163">Definisce le funzionalità di sicurezza per [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="6c03a-163">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6c03a-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c03a-164">Example</span></span>  
 <span data-ttu-id="6c03a-165">Nell'esempio seguente è dimostrato l'uso della sicurezza del trasporto SSL con l'associazione di base.</span><span class="sxs-lookup"><span data-stu-id="6c03a-165">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="6c03a-166">Per impostazione predefinita, l'associazione di base supporta la comunicazione HTTP.</span><span class="sxs-lookup"><span data-stu-id="6c03a-166">By default, the basic binding supports HTTP communication.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c03a-167">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6c03a-167">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="6c03a-168">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="6c03a-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6c03a-169">Binding</span><span class="sxs-lookup"><span data-stu-id="6c03a-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6c03a-170">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="6c03a-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6c03a-171">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="6c03a-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
