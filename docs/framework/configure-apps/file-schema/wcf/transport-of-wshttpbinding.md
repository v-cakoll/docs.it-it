---
title: <transport> di <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 384267e3d018d714f95356461eb303bc9ec0cb3e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934631"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="e3331-102">\<> di trasporto \<di WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e3331-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="e3331-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="e3331-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="e3331-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e3331-104">\<system.serviceModel></span></span>\
<span data-ttu-id="e3331-105">\<Binding > </span><span class="sxs-lookup"><span data-stu-id="e3331-105">\<bindings></span></span>\
<span data-ttu-id="e3331-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e3331-106">\<wsHttpBinding></span></span>\
<span data-ttu-id="e3331-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="e3331-107">\<binding></span></span>\
<span data-ttu-id="e3331-108">\<> sicurezza </span><span class="sxs-lookup"><span data-stu-id="e3331-108">\<security></span></span>\
<span data-ttu-id="e3331-109">\<> di trasporto</span><span class="sxs-lookup"><span data-stu-id="e3331-109">\<transport></span></span>

## <a name="syntax"></a><span data-ttu-id="e3331-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3331-110">Syntax</span></span>

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

## <a name="type"></a><span data-ttu-id="e3331-111">Type</span><span class="sxs-lookup"><span data-stu-id="e3331-111">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="e3331-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e3331-112">Attributes and Elements</span></span>

<span data-ttu-id="e3331-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e3331-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3331-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="e3331-114">Attributes</span></span>

|<span data-ttu-id="e3331-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="e3331-115">Attribute</span></span>|<span data-ttu-id="e3331-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3331-116">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="e3331-117">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="e3331-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="e3331-118">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e3331-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="e3331-119">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="e3331-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="e3331-120">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e3331-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="e3331-121">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="e3331-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="e3331-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e3331-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="e3331-123">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="e3331-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="e3331-124">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="e3331-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="e3331-125">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="e3331-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="e3331-126">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="e3331-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="e3331-127">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e3331-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="e3331-128">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="e3331-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="e3331-129">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="e3331-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="e3331-130">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e3331-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="e3331-131">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e3331-131">clientCredentialType Attribute</span></span>

|<span data-ttu-id="e3331-132">Value</span><span class="sxs-lookup"><span data-stu-id="e3331-132">Value</span></span>|<span data-ttu-id="e3331-133">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="e3331-133">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="e3331-134">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e3331-134">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="e3331-135">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="e3331-135">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="e3331-136">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="e3331-136">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="e3331-137">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="e3331-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="e3331-138">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="e3331-138">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="e3331-139">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="e3331-139">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="e3331-140">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="e3331-140">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="e3331-141">Valore</span><span class="sxs-lookup"><span data-stu-id="e3331-141">Value</span></span>|<span data-ttu-id="e3331-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3331-142">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="e3331-143">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e3331-143">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="e3331-144">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="e3331-144">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="e3331-145">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="e3331-145">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="e3331-146">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="e3331-146">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="e3331-147">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="e3331-147">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="e3331-148">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="e3331-148">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e3331-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e3331-149">Child Elements</span></span>

<span data-ttu-id="e3331-150">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e3331-150">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e3331-151">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e3331-151">Parent Elements</span></span>

|<span data-ttu-id="e3331-152">Elemento</span><span class="sxs-lookup"><span data-stu-id="e3331-152">Element</span></span>|<span data-ttu-id="e3331-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3331-153">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3331-154">\<security></span><span class="sxs-lookup"><span data-stu-id="e3331-154">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="e3331-155">Rappresenta le funzionalità di sicurezza di [ \<WSHttpBinding >](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="e3331-155">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="e3331-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3331-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="e3331-157">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="e3331-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e3331-158">Associazioni</span><span class="sxs-lookup"><span data-stu-id="e3331-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e3331-159">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="e3331-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e3331-160">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="e3331-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e3331-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="e3331-161">\<binding></span></span>](../../../misc/binding.md)
