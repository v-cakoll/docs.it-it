---
title: <transport> di <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: a1540b53d4af76141c1daee60a6bddbbecd9d6da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788297"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="3a8e1-102">\<Transport > di \<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3a8e1-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="3a8e1-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="3a8e1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3a8e1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3a8e1-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="3a8e1-105">\<bindings></span></span>  
<span data-ttu-id="3a8e1-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="3a8e1-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="3a8e1-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="3a8e1-107">\<binding></span></span>  
<span data-ttu-id="3a8e1-108">\<security></span><span class="sxs-lookup"><span data-stu-id="3a8e1-108">\<security></span></span>  
<span data-ttu-id="3a8e1-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="3a8e1-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a8e1-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a8e1-110">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="3a8e1-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="3a8e1-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a8e1-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3a8e1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3a8e1-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a8e1-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="3a8e1-114">Attributes</span></span>  
  
|<span data-ttu-id="3a8e1-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="3a8e1-115">Attribute</span></span>|<span data-ttu-id="3a8e1-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a8e1-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="3a8e1-117">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="3a8e1-118">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="3a8e1-119">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="3a8e1-120">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="3a8e1-121">L'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="3a8e1-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="3a8e1-123">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="3a8e1-124">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="3a8e1-125">Un utente può eseguire una query nell'area di autenticazione per determinare quale dei vari possibili nomi utente e password possono essere usati.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="3a8e1-126">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="3a8e1-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3a8e1-127">Value</span><span class="sxs-lookup"><span data-stu-id="3a8e1-127">Value</span></span>|<span data-ttu-id="3a8e1-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a8e1-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3a8e1-129">nessuno</span><span class="sxs-lookup"><span data-stu-id="3a8e1-129">None</span></span>|<span data-ttu-id="3a8e1-130">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-130">Security is disabled.</span></span>|  
|<span data-ttu-id="3a8e1-131">Basic</span><span class="sxs-lookup"><span data-stu-id="3a8e1-131">Basic</span></span>|<span data-ttu-id="3a8e1-132">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="3a8e1-133">Digest</span><span class="sxs-lookup"><span data-stu-id="3a8e1-133">Digest</span></span>|<span data-ttu-id="3a8e1-134">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="3a8e1-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="3a8e1-135">Ntlm</span></span>|<span data-ttu-id="3a8e1-136">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="3a8e1-137">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="3a8e1-137">Windows</span></span>|<span data-ttu-id="3a8e1-138">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="3a8e1-139">Certificato</span><span class="sxs-lookup"><span data-stu-id="3a8e1-139">Certificate</span></span>|<span data-ttu-id="3a8e1-140">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="3a8e1-141">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="3a8e1-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3a8e1-142">Value</span><span class="sxs-lookup"><span data-stu-id="3a8e1-142">Value</span></span>|<span data-ttu-id="3a8e1-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a8e1-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3a8e1-144">nessuno</span><span class="sxs-lookup"><span data-stu-id="3a8e1-144">None</span></span>|<span data-ttu-id="3a8e1-145">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-145">Security is disabled.</span></span>|  
|<span data-ttu-id="3a8e1-146">Basic</span><span class="sxs-lookup"><span data-stu-id="3a8e1-146">Basic</span></span>|<span data-ttu-id="3a8e1-147">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="3a8e1-148">Digest</span><span class="sxs-lookup"><span data-stu-id="3a8e1-148">Digest</span></span>|<span data-ttu-id="3a8e1-149">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="3a8e1-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="3a8e1-150">Ntlm</span></span>|<span data-ttu-id="3a8e1-151">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="3a8e1-152">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="3a8e1-152">Windows</span></span>|<span data-ttu-id="3a8e1-153">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="3a8e1-154">Certificato</span><span class="sxs-lookup"><span data-stu-id="3a8e1-154">Certificate</span></span>|<span data-ttu-id="3a8e1-155">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a8e1-156">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3a8e1-156">Child Elements</span></span>  
 <span data-ttu-id="3a8e1-157">nessuno</span><span class="sxs-lookup"><span data-stu-id="3a8e1-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a8e1-158">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3a8e1-158">Parent Elements</span></span>  
  
|<span data-ttu-id="3a8e1-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a8e1-159">Element</span></span>|<span data-ttu-id="3a8e1-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a8e1-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a8e1-161">\<security></span><span class="sxs-lookup"><span data-stu-id="3a8e1-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="3a8e1-162">Rappresenta le funzionalità di protezione del [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="3a8e1-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a8e1-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a8e1-163">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="3a8e1-164">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="3a8e1-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3a8e1-165">Associazioni</span><span class="sxs-lookup"><span data-stu-id="3a8e1-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="3a8e1-166">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="3a8e1-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3a8e1-167">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="3a8e1-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3a8e1-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="3a8e1-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
