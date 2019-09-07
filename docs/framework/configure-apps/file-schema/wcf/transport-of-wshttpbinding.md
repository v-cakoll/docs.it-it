---
title: <transport> di <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 95cfa076f62f767af431ff5a0bcc2ca31b824e30
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399234"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="11720-102">\<> di trasporto \<di WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="11720-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="11720-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="11720-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="11720-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="11720-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="11720-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="11720-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="11720-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="11720-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="11720-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> WSHttpBinding**](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="11720-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="11720-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="11720-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="11720-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="11720-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)</span></span>\
<span data-ttu-id="11720-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di trasporto**</span><span class="sxs-lookup"><span data-stu-id="11720-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="11720-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11720-111">Syntax</span></span>

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

## <a name="type"></a><span data-ttu-id="11720-112">Type</span><span class="sxs-lookup"><span data-stu-id="11720-112">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="11720-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="11720-113">Attributes and Elements</span></span>

<span data-ttu-id="11720-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="11720-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="11720-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="11720-115">Attributes</span></span>

|<span data-ttu-id="11720-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="11720-116">Attribute</span></span>|<span data-ttu-id="11720-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="11720-117">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="11720-118">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="11720-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="11720-119">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="11720-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="11720-120">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="11720-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="11720-121">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="11720-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="11720-122">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="11720-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="11720-123">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="11720-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="11720-124">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="11720-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="11720-125">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="11720-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="11720-126">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="11720-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="11720-127">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="11720-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="11720-128">1.  Never – I criteri non vengono mai applicati e la protezione estesa è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="11720-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="11720-129">2.  WhenSupported – I criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="11720-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="11720-130">3.  Always - I criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="11720-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="11720-131">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="11720-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="11720-132">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="11720-132">clientCredentialType Attribute</span></span>

|<span data-ttu-id="11720-133">Value</span><span class="sxs-lookup"><span data-stu-id="11720-133">Value</span></span>|<span data-ttu-id="11720-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11720-134">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="11720-135">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="11720-135">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="11720-136">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="11720-136">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="11720-137">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="11720-137">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="11720-138">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="11720-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="11720-139">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="11720-139">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="11720-140">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="11720-140">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="11720-141">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="11720-141">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="11720-142">Value</span><span class="sxs-lookup"><span data-stu-id="11720-142">Value</span></span>|<span data-ttu-id="11720-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11720-143">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="11720-144">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="11720-144">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="11720-145">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="11720-145">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="11720-146">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="11720-146">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="11720-147">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="11720-147">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="11720-148">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="11720-148">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="11720-149">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="11720-149">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="11720-150">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="11720-150">Child Elements</span></span>

<span data-ttu-id="11720-151">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="11720-151">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="11720-152">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="11720-152">Parent Elements</span></span>

|<span data-ttu-id="11720-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="11720-153">Element</span></span>|<span data-ttu-id="11720-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11720-154">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="11720-155">\<security></span><span class="sxs-lookup"><span data-stu-id="11720-155">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="11720-156">Rappresenta le funzionalità di sicurezza di [ \<WSHttpBinding >](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="11720-156">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="11720-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11720-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="11720-158">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="11720-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="11720-159">Associazioni</span><span class="sxs-lookup"><span data-stu-id="11720-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="11720-160">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="11720-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="11720-161">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="11720-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="11720-162">\<binding></span><span class="sxs-lookup"><span data-stu-id="11720-162">\<binding></span></span>](../../../misc/binding.md)
