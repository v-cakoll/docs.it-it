---
title: <transport> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: f78add5397644dc40bfd22f10bd84aa5c5eb29e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923204"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="593bc-102">\<> di trasporto \<di WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="593bc-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="593bc-103">Definisce le impostazioni di sicurezza a livello di trasporto per un endpoint del servizio configurato per ricevere richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="593bc-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="593bc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="593bc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="593bc-105">\<Binding ></span><span class="sxs-lookup"><span data-stu-id="593bc-105">\<bindings></span></span>  
<span data-ttu-id="593bc-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="593bc-106">\<webHttpBinding></span></span>  
<span data-ttu-id="593bc-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="593bc-107">\<binding></span></span>  
<span data-ttu-id="593bc-108">\<security></span><span class="sxs-lookup"><span data-stu-id="593bc-108">\<security></span></span>  
<span data-ttu-id="593bc-109">\<> di trasporto</span><span class="sxs-lookup"><span data-stu-id="593bc-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="593bc-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="593bc-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>
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
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="593bc-111">Type</span><span class="sxs-lookup"><span data-stu-id="593bc-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="593bc-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="593bc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="593bc-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="593bc-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="593bc-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="593bc-114">Attributes</span></span>  
  
|<span data-ttu-id="593bc-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="593bc-115">Attribute</span></span>|<span data-ttu-id="593bc-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="593bc-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="593bc-117">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="593bc-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="593bc-118">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="593bc-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="593bc-119">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="593bc-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="593bc-120">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="593bc-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="593bc-121">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="593bc-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="593bc-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="593bc-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="593bc-123">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="593bc-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="593bc-124">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="593bc-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="593bc-125">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="593bc-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="593bc-126">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="593bc-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="593bc-127">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="593bc-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="593bc-128">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="593bc-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="593bc-129">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="593bc-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="593bc-130">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="593bc-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="593bc-131">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="593bc-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="593bc-132">Value</span><span class="sxs-lookup"><span data-stu-id="593bc-132">Value</span></span>|<span data-ttu-id="593bc-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="593bc-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="593bc-134">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="593bc-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="593bc-135">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="593bc-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="593bc-136">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="593bc-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="593bc-137">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="593bc-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="593bc-138">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="593bc-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="593bc-139">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="593bc-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="593bc-140">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="593bc-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="593bc-141">Value</span><span class="sxs-lookup"><span data-stu-id="593bc-141">Value</span></span>|<span data-ttu-id="593bc-142">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="593bc-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="593bc-143">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="593bc-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="593bc-144">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="593bc-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="593bc-145">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="593bc-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="593bc-146">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="593bc-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="593bc-147">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="593bc-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="593bc-148">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="593bc-148">Child Elements</span></span>  
 <span data-ttu-id="593bc-149">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="593bc-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="593bc-150">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="593bc-150">Parent Elements</span></span>  
  
|<span data-ttu-id="593bc-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="593bc-151">Element</span></span>|<span data-ttu-id="593bc-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="593bc-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="593bc-153">\<security></span><span class="sxs-lookup"><span data-stu-id="593bc-153">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="593bc-154">Rappresenta le funzionalità di sicurezza dell' [ \<elemento > WSHttpBinding](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="593bc-154">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="593bc-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="593bc-155">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="593bc-156">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="593bc-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="593bc-157">Associazioni</span><span class="sxs-lookup"><span data-stu-id="593bc-157">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="593bc-158">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="593bc-158">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="593bc-159">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="593bc-159">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="593bc-160">\<binding></span><span class="sxs-lookup"><span data-stu-id="593bc-160">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="593bc-161">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="593bc-161">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
