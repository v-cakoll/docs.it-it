---
title: <transport> di <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732733"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="91db6-102">\<transport> di \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="91db6-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="91db6-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="91db6-103">Defines authentication settings for the HTTP transport.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  

## <a name="syntax"></a><span data-ttu-id="91db6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91db6-104">Syntax</span></span>

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

## <a name="type"></a><span data-ttu-id="91db6-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="91db6-105">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="91db6-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="91db6-106">Attributes and Elements</span></span>

<span data-ttu-id="91db6-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="91db6-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="91db6-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="91db6-108">Attributes</span></span>

|<span data-ttu-id="91db6-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="91db6-109">Attribute</span></span>|<span data-ttu-id="91db6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91db6-110">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="91db6-111">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="91db6-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="91db6-112">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="91db6-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="91db6-113">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="91db6-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="91db6-114">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="91db6-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="91db6-115">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="91db6-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="91db6-116">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="91db6-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="91db6-117">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="91db6-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="91db6-118">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="91db6-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="91db6-119">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="91db6-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="91db6-120">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="91db6-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="91db6-121">1. Never: il criterio non viene mai applicato (la protezione estesa è disabilitata).</span><span class="sxs-lookup"><span data-stu-id="91db6-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="91db6-122">2. WhenSupported: i criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="91db6-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="91db6-123">3. always: i criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="91db6-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="91db6-124">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="91db6-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="91db6-125">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="91db6-125">clientCredentialType Attribute</span></span>

|<span data-ttu-id="91db6-126">Valore</span><span class="sxs-lookup"><span data-stu-id="91db6-126">Value</span></span>|<span data-ttu-id="91db6-127">Description</span><span class="sxs-lookup"><span data-stu-id="91db6-127">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="91db6-128">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="91db6-128">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="91db6-129">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="91db6-129">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="91db6-130">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="91db6-130">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="91db6-131">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="91db6-131">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="91db6-132">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="91db6-132">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="91db6-133">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="91db6-133">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="91db6-134">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="91db6-134">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="91db6-135">Valore</span><span class="sxs-lookup"><span data-stu-id="91db6-135">Value</span></span>|<span data-ttu-id="91db6-136">Description</span><span class="sxs-lookup"><span data-stu-id="91db6-136">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="91db6-137">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="91db6-137">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="91db6-138">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="91db6-138">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="91db6-139">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="91db6-139">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="91db6-140">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="91db6-140">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="91db6-141">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="91db6-141">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="91db6-142">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="91db6-142">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="91db6-143">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="91db6-143">Child Elements</span></span>

<span data-ttu-id="91db6-144">No.</span><span class="sxs-lookup"><span data-stu-id="91db6-144">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="91db6-145">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="91db6-145">Parent Elements</span></span>

|<span data-ttu-id="91db6-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="91db6-146">Element</span></span>|<span data-ttu-id="91db6-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91db6-147">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="91db6-148">Rappresenta le funzionalità di sicurezza di [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="91db6-148">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="91db6-149">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="91db6-149">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="91db6-150">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="91db6-150">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="91db6-151">Binding</span><span class="sxs-lookup"><span data-stu-id="91db6-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="91db6-152">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="91db6-152">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="91db6-153">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="91db6-153">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
