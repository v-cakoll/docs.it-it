---
title: <transport> di <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732733"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="5d7b3-102">\<> di trasporto di \<WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="5d7b3-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="5d7b3-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="5d7b3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d7b3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d7b3-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5d7b3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5d7b3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**Binding**](bindings.md)\<</span><span class="sxs-lookup"><span data-stu-id="5d7b3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="5d7b3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**wsHttpBinding**](wshttpbinding.md)\<</span><span class="sxs-lookup"><span data-stu-id="5d7b3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\</span></span>
<span data-ttu-id="5d7b3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Binding** ></span><span class="sxs-lookup"><span data-stu-id="5d7b3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="5d7b3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**sicurezza**](security-of-wshttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="5d7b3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)</span></span>\
<span data-ttu-id="5d7b3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport** ></span><span class="sxs-lookup"><span data-stu-id="5d7b3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="5d7b3-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d7b3-111">Syntax</span></span>

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
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a><span data-ttu-id="5d7b3-112">Digitare</span><span class="sxs-lookup"><span data-stu-id="5d7b3-112">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="5d7b3-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5d7b3-113">Attributes and Elements</span></span>

<span data-ttu-id="5d7b3-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5d7b3-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="5d7b3-115">Attributes</span></span>

|<span data-ttu-id="5d7b3-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="5d7b3-116">Attribute</span></span>|<span data-ttu-id="5d7b3-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d7b3-117">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="5d7b3-118">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="5d7b3-119">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="5d7b3-120">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="5d7b3-121">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="5d7b3-122">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="5d7b3-123">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="5d7b3-124">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="5d7b3-125">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="5d7b3-126">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="5d7b3-127">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="5d7b3-128">1. Never: il criterio non viene mai applicato (la protezione estesa è disabilitata).</span><span class="sxs-lookup"><span data-stu-id="5d7b3-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="5d7b3-129">2. WhenSupported: i criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="5d7b3-130">3. always: i criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="5d7b3-131">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="5d7b3-132">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="5d7b3-132">clientCredentialType Attribute</span></span>

|<span data-ttu-id="5d7b3-133">Value</span><span class="sxs-lookup"><span data-stu-id="5d7b3-133">Value</span></span>|<span data-ttu-id="5d7b3-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d7b3-134">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="5d7b3-135">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-135">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="5d7b3-136">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-136">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="5d7b3-137">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-137">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="5d7b3-138">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="5d7b3-139">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-139">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="5d7b3-140">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-140">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="5d7b3-141">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="5d7b3-141">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="5d7b3-142">Value</span><span class="sxs-lookup"><span data-stu-id="5d7b3-142">Value</span></span>|<span data-ttu-id="5d7b3-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d7b3-143">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="5d7b3-144">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-144">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="5d7b3-145">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-145">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="5d7b3-146">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-146">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="5d7b3-147">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-147">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="5d7b3-148">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-148">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="5d7b3-149">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-149">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5d7b3-150">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5d7b3-150">Child Elements</span></span>

<span data-ttu-id="5d7b3-151">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="5d7b3-151">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5d7b3-152">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5d7b3-152">Parent Elements</span></span>

|<span data-ttu-id="5d7b3-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d7b3-153">Element</span></span>|<span data-ttu-id="5d7b3-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d7b3-154">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="5d7b3-155">\<security ></span><span class="sxs-lookup"><span data-stu-id="5d7b3-155">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="5d7b3-156">Rappresenta le funzionalità di sicurezza di [\<wshttpbinding >](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5d7b3-156">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="5d7b3-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d7b3-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="5d7b3-158">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="5d7b3-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5d7b3-159">Associazioni</span><span class="sxs-lookup"><span data-stu-id="5d7b3-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5d7b3-160">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="5d7b3-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5d7b3-161">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="5d7b3-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5d7b3-162">\<binding ></span><span class="sxs-lookup"><span data-stu-id="5d7b3-162">\<binding></span></span>](bindings.md)
