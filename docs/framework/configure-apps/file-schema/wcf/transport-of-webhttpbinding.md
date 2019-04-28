---
title: <transport> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: 8dcd51cd248dbba3ccf60295cb1712167684328e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788271"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="426d2-102">\<Transport > di \<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="426d2-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="426d2-103">Definisce le impostazioni di sicurezza a livello di trasporto per un endpoint del servizio configurato per ricevere richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="426d2-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="426d2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="426d2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="426d2-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="426d2-105">\<bindings></span></span>  
<span data-ttu-id="426d2-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="426d2-106">\<webHttpBinding></span></span>  
<span data-ttu-id="426d2-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="426d2-107">\<binding></span></span>  
<span data-ttu-id="426d2-108">\<security></span><span class="sxs-lookup"><span data-stu-id="426d2-108">\<security></span></span>  
<span data-ttu-id="426d2-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="426d2-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="426d2-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="426d2-110">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="426d2-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="426d2-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="426d2-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="426d2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="426d2-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="426d2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="426d2-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="426d2-114">Attributes</span></span>  
  
|<span data-ttu-id="426d2-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="426d2-115">Attribute</span></span>|<span data-ttu-id="426d2-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="426d2-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="426d2-117">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="426d2-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="426d2-118">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="426d2-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="426d2-119">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="426d2-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="426d2-120">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="426d2-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="426d2-121">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="426d2-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="426d2-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="426d2-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="426d2-123">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="426d2-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="426d2-124">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="426d2-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="426d2-125">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="426d2-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="426d2-126">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="426d2-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="426d2-127">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="426d2-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="426d2-128">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="426d2-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="426d2-129">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="426d2-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="426d2-130">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="426d2-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="426d2-131">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="426d2-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="426d2-132">Value</span><span class="sxs-lookup"><span data-stu-id="426d2-132">Value</span></span>|<span data-ttu-id="426d2-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="426d2-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="426d2-134">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="426d2-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="426d2-135">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="426d2-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="426d2-136">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="426d2-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="426d2-137">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="426d2-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="426d2-138">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="426d2-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="426d2-139">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="426d2-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="426d2-140">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="426d2-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="426d2-141">Value</span><span class="sxs-lookup"><span data-stu-id="426d2-141">Value</span></span>|<span data-ttu-id="426d2-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="426d2-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="426d2-143">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="426d2-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="426d2-144">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="426d2-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="426d2-145">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="426d2-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="426d2-146">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="426d2-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="426d2-147">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="426d2-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="426d2-148">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="426d2-148">Child Elements</span></span>  
 <span data-ttu-id="426d2-149">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="426d2-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="426d2-150">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="426d2-150">Parent Elements</span></span>  
  
|<span data-ttu-id="426d2-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="426d2-151">Element</span></span>|<span data-ttu-id="426d2-152">Descrizione</span><span class="sxs-lookup"><span data-stu-id="426d2-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="426d2-153">\<security></span><span class="sxs-lookup"><span data-stu-id="426d2-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|<span data-ttu-id="426d2-154">Rappresenta le funzionalità di protezione del [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="426d2-154">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="426d2-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="426d2-155">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="426d2-156">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="426d2-156">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="426d2-157">Associazioni</span><span class="sxs-lookup"><span data-stu-id="426d2-157">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="426d2-158">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="426d2-158">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="426d2-159">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="426d2-159">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="426d2-160">\<binding></span><span class="sxs-lookup"><span data-stu-id="426d2-160">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="426d2-161">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="426d2-161">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
