---
title: <transport> di <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732796"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="e2472-102">\<transport> di \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e2472-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="e2472-103">Definisce le impostazioni di sicurezza a livello di trasporto per un endpoint del servizio configurato per ricevere richieste HTTP.</span><span class="sxs-lookup"><span data-stu-id="e2472-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="e2472-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2472-104">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="e2472-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="e2472-105">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2472-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e2472-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e2472-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e2472-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2472-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="e2472-108">Attributes</span></span>  
  
|<span data-ttu-id="e2472-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="e2472-109">Attribute</span></span>|<span data-ttu-id="e2472-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2472-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="e2472-111">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="e2472-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="e2472-112">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e2472-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="e2472-113">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="e2472-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="e2472-114">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e2472-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="e2472-115">Stringa che specifica l'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="e2472-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="e2472-116">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="e2472-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="e2472-117">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="e2472-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="e2472-118">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="e2472-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="e2472-119">Un utente può eseguire una query nell'area di autenticazione per verificare i nomi utente e le password da usare tra quelli possibili.</span><span class="sxs-lookup"><span data-stu-id="e2472-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="e2472-120">Questa enumerazione specifica il momento in cui deve essere applicato l'oggetto <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="e2472-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="e2472-121">1. Never: il criterio non viene mai applicato (la protezione estesa è disabilitata).</span><span class="sxs-lookup"><span data-stu-id="e2472-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="e2472-122">2. WhenSupported: i criteri vengono applicati solo se il client supporta la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="e2472-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="e2472-123">3. always: i criteri vengono sempre applicati.</span><span class="sxs-lookup"><span data-stu-id="e2472-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="e2472-124">L'autenticazione dei client che non supportano la protezione estesa avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="e2472-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="e2472-125">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e2472-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e2472-126">Valore</span><span class="sxs-lookup"><span data-stu-id="e2472-126">Value</span></span>|<span data-ttu-id="e2472-127">Description</span><span class="sxs-lookup"><span data-stu-id="e2472-127">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="e2472-128">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e2472-128">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="e2472-129">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="e2472-129">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="e2472-130">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="e2472-130">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="e2472-131">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="e2472-131">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="e2472-132">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="e2472-132">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="e2472-133">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="e2472-133">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="e2472-134">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="e2472-134">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e2472-135">Valore</span><span class="sxs-lookup"><span data-stu-id="e2472-135">Value</span></span>|<span data-ttu-id="e2472-136">Description</span><span class="sxs-lookup"><span data-stu-id="e2472-136">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="e2472-137">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="e2472-137">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="e2472-138">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="e2472-138">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="e2472-139">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="e2472-139">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="e2472-140">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="e2472-140">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="e2472-141">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="e2472-141">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2472-142">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e2472-142">Child Elements</span></span>  
 <span data-ttu-id="e2472-143">No.</span><span class="sxs-lookup"><span data-stu-id="e2472-143">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2472-144">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e2472-144">Parent Elements</span></span>  
  
|<span data-ttu-id="e2472-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2472-145">Element</span></span>|<span data-ttu-id="e2472-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2472-146">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|<span data-ttu-id="e2472-147">Rappresenta le funzionalità di sicurezza dell' [\<wsHttpBinding>](wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e2472-147">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2472-148">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e2472-148">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="e2472-149">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="e2472-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e2472-150">Binding</span><span class="sxs-lookup"><span data-stu-id="e2472-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e2472-151">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="e2472-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e2472-152">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="e2472-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="e2472-153">Modello di programmazione HTTP Web WCF</span><span class="sxs-lookup"><span data-stu-id="e2472-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
