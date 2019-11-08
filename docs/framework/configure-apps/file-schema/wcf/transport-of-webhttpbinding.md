---
title: <transport> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732796"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="d28bd-102">\<> di trasporto di \<WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d28bd-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="d28bd-103">Definisce le impostazioni di sicurezza a livello di trasporto per un endpoint del servizio configurato per ricevere richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="d28bd-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
<span data-ttu-id="d28bd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d28bd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d28bd-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d28bd-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d28bd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="d28bd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="d28bd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**WebHttpBinding**](webhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="d28bd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="d28bd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="d28bd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d28bd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**sicurezza**](security-of-webhttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="d28bd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)</span></span>\
<span data-ttu-id="d28bd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport** ></span><span class="sxs-lookup"><span data-stu-id="d28bd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d28bd-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d28bd-111">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="d28bd-112">Digitare</span><span class="sxs-lookup"><span data-stu-id="d28bd-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d28bd-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d28bd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d28bd-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d28bd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d28bd-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="d28bd-115">Attributes</span></span>  
  
|<span data-ttu-id="d28bd-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="d28bd-116">Attribute</span></span>|<span data-ttu-id="d28bd-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d28bd-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="d28bd-118">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="d28bd-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="d28bd-119">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d28bd-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="d28bd-120">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="d28bd-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="d28bd-121">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d28bd-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="d28bd-122">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="d28bd-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="d28bd-123">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="d28bd-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="d28bd-124">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d28bd-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="d28bd-125">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="d28bd-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="d28bd-126">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="d28bd-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="d28bd-127">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="d28bd-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="d28bd-128">1. Never: il criterio non viene mai applicato (la protezione estesa è disabilitata).</span><span class="sxs-lookup"><span data-stu-id="d28bd-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="d28bd-129">2. WhenSupported: i criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="d28bd-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="d28bd-130">3. always: i criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="d28bd-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="d28bd-131">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d28bd-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="d28bd-132">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d28bd-132">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="d28bd-133">Value</span><span class="sxs-lookup"><span data-stu-id="d28bd-133">Value</span></span>|<span data-ttu-id="d28bd-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d28bd-134">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="d28bd-135">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d28bd-135">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="d28bd-136">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="d28bd-136">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="d28bd-137">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="d28bd-137">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="d28bd-138">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="d28bd-138">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="d28bd-139">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="d28bd-139">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="d28bd-140">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="d28bd-140">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="d28bd-141">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="d28bd-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="d28bd-142">Value</span><span class="sxs-lookup"><span data-stu-id="d28bd-142">Value</span></span>|<span data-ttu-id="d28bd-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d28bd-143">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="d28bd-144">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d28bd-144">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="d28bd-145">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="d28bd-145">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="d28bd-146">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="d28bd-146">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="d28bd-147">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="d28bd-147">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="d28bd-148">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="d28bd-148">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d28bd-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d28bd-149">Child Elements</span></span>  
 <span data-ttu-id="d28bd-150">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="d28bd-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d28bd-151">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d28bd-151">Parent Elements</span></span>  
  
|<span data-ttu-id="d28bd-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="d28bd-152">Element</span></span>|<span data-ttu-id="d28bd-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d28bd-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d28bd-154">\<security ></span><span class="sxs-lookup"><span data-stu-id="d28bd-154">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="d28bd-155">Rappresenta le funzionalità di sicurezza dell'elemento [> WSHttpBinding di\<](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="d28bd-155">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d28bd-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d28bd-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="d28bd-157">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="d28bd-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d28bd-158">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d28bd-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d28bd-159">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d28bd-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d28bd-160">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="d28bd-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d28bd-161">\<binding ></span><span class="sxs-lookup"><span data-stu-id="d28bd-161">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="d28bd-162">Modello di programmazione HTTP Web di WCF</span><span class="sxs-lookup"><span data-stu-id="d28bd-162">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
