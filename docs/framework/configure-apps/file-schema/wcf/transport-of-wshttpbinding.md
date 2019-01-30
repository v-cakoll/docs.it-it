---
title: <transport> di <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1c25ffd70ae83f14d5e596b1ee32d05abcc95184
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267677"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="f406a-102">\<Transport > di \<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f406a-102">\<transport> of \<wsHttpBinding></span></span>
<span data-ttu-id="f406a-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="f406a-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="f406a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f406a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f406a-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="f406a-105">\<bindings></span></span>  
<span data-ttu-id="f406a-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f406a-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="f406a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f406a-107">\<binding></span></span>  
<span data-ttu-id="f406a-108">\<security></span><span class="sxs-lookup"><span data-stu-id="f406a-108">\<security></span></span>  
<span data-ttu-id="f406a-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="f406a-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f406a-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f406a-110">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtecutionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="f406a-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="f406a-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f406a-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f406a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f406a-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f406a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f406a-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="f406a-114">Attributes</span></span>  
  
|<span data-ttu-id="f406a-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="f406a-115">Attribute</span></span>|<span data-ttu-id="f406a-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f406a-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="f406a-117">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="f406a-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="f406a-118">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f406a-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="f406a-119">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="f406a-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="f406a-120">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f406a-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="f406a-121">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="f406a-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="f406a-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="f406a-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="f406a-123">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f406a-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="f406a-124">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="f406a-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="f406a-125">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="f406a-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="f406a-126">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="f406a-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="f406a-127">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f406a-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="f406a-128">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="f406a-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="f406a-129">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="f406a-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="f406a-130">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f406a-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="f406a-131">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="f406a-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f406a-132">Valore</span><span class="sxs-lookup"><span data-stu-id="f406a-132">Value</span></span>|<span data-ttu-id="f406a-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f406a-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="f406a-134">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f406a-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="f406a-135">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="f406a-135">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="f406a-136">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="f406a-136">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="f406a-137">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="f406a-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="f406a-138">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="f406a-138">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="f406a-139">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="f406a-139">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="f406a-140">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="f406a-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f406a-141">Valore</span><span class="sxs-lookup"><span data-stu-id="f406a-141">Value</span></span>|<span data-ttu-id="f406a-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f406a-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="f406a-143">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f406a-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="f406a-144">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="f406a-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="f406a-145">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="f406a-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="f406a-146">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="f406a-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="f406a-147">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="f406a-147">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="f406a-148">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="f406a-148">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f406a-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f406a-149">Child Elements</span></span>  
 <span data-ttu-id="f406a-150">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f406a-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f406a-151">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f406a-151">Parent Elements</span></span>  
  
|<span data-ttu-id="f406a-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="f406a-152">Element</span></span>|<span data-ttu-id="f406a-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f406a-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f406a-154">\<security></span><span class="sxs-lookup"><span data-stu-id="f406a-154">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="f406a-155">Rappresenta le funzionalità di protezione del [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f406a-155">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f406a-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f406a-156">See also</span></span>
- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="f406a-157">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="f406a-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f406a-158">Associazioni</span><span class="sxs-lookup"><span data-stu-id="f406a-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f406a-159">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="f406a-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f406a-160">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="f406a-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f406a-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="f406a-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
