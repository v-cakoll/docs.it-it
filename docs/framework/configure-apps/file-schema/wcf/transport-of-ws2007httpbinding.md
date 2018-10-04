---
title: '&lt;transport&gt; di &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 5c7e96beee2fc1e4780729e56f10a52b63dde4e8
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48580063"
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="269e9-102">&lt;transport&gt; di &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="269e9-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="269e9-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="269e9-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="269e9-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="269e9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="269e9-105">\<le associazioni ></span><span class="sxs-lookup"><span data-stu-id="269e9-105">\<bindings></span></span>  
<span data-ttu-id="269e9-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="269e9-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="269e9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="269e9-107">\<binding></span></span>  
<span data-ttu-id="269e9-108">\<security></span><span class="sxs-lookup"><span data-stu-id="269e9-108">\<security></span></span>  
<span data-ttu-id="269e9-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="269e9-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="269e9-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="269e9-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="269e9-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="269e9-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="269e9-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="269e9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="269e9-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="269e9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="269e9-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="269e9-114">Attributes</span></span>  
  
|<span data-ttu-id="269e9-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="269e9-115">Attribute</span></span>|<span data-ttu-id="269e9-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="269e9-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="269e9-117">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="269e9-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="269e9-118">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="269e9-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="269e9-119">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="269e9-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="269e9-120">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="269e9-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="269e9-121">L'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="269e9-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="269e9-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="269e9-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="269e9-123">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="269e9-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="269e9-124">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="269e9-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="269e9-125">Un utente può eseguire una query nell'area di autenticazione per determinare quale dei vari possibili nomi utente e password possono essere usati.</span><span class="sxs-lookup"><span data-stu-id="269e9-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="269e9-126">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="269e9-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="269e9-127">Valore</span><span class="sxs-lookup"><span data-stu-id="269e9-127">Value</span></span>|<span data-ttu-id="269e9-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="269e9-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="269e9-129">None</span><span class="sxs-lookup"><span data-stu-id="269e9-129">None</span></span>|<span data-ttu-id="269e9-130">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="269e9-130">Security is disabled.</span></span>|  
|<span data-ttu-id="269e9-131">Di base</span><span class="sxs-lookup"><span data-stu-id="269e9-131">Basic</span></span>|<span data-ttu-id="269e9-132">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="269e9-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="269e9-133">Digest</span><span class="sxs-lookup"><span data-stu-id="269e9-133">Digest</span></span>|<span data-ttu-id="269e9-134">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="269e9-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="269e9-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="269e9-135">Ntlm</span></span>|<span data-ttu-id="269e9-136">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="269e9-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="269e9-137">Windows</span><span class="sxs-lookup"><span data-stu-id="269e9-137">Windows</span></span>|<span data-ttu-id="269e9-138">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="269e9-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="269e9-139">Certificato</span><span class="sxs-lookup"><span data-stu-id="269e9-139">Certificate</span></span>|<span data-ttu-id="269e9-140">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="269e9-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="269e9-141">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="269e9-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="269e9-142">Valore</span><span class="sxs-lookup"><span data-stu-id="269e9-142">Value</span></span>|<span data-ttu-id="269e9-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="269e9-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="269e9-144">None</span><span class="sxs-lookup"><span data-stu-id="269e9-144">None</span></span>|<span data-ttu-id="269e9-145">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="269e9-145">Security is disabled.</span></span>|  
|<span data-ttu-id="269e9-146">Di base</span><span class="sxs-lookup"><span data-stu-id="269e9-146">Basic</span></span>|<span data-ttu-id="269e9-147">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="269e9-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="269e9-148">Digest</span><span class="sxs-lookup"><span data-stu-id="269e9-148">Digest</span></span>|<span data-ttu-id="269e9-149">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="269e9-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="269e9-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="269e9-150">Ntlm</span></span>|<span data-ttu-id="269e9-151">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="269e9-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="269e9-152">Windows</span><span class="sxs-lookup"><span data-stu-id="269e9-152">Windows</span></span>|<span data-ttu-id="269e9-153">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="269e9-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="269e9-154">Certificato</span><span class="sxs-lookup"><span data-stu-id="269e9-154">Certificate</span></span>|<span data-ttu-id="269e9-155">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="269e9-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="269e9-156">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="269e9-156">Child Elements</span></span>  
 <span data-ttu-id="269e9-157">nessuno</span><span class="sxs-lookup"><span data-stu-id="269e9-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="269e9-158">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="269e9-158">Parent Elements</span></span>  
  
|<span data-ttu-id="269e9-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="269e9-159">Element</span></span>|<span data-ttu-id="269e9-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="269e9-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="269e9-161">\<security></span><span class="sxs-lookup"><span data-stu-id="269e9-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="269e9-162">Rappresenta le funzionalità di protezione del [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="269e9-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="269e9-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="269e9-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="269e9-164">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="269e9-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="269e9-165">Associazioni</span><span class="sxs-lookup"><span data-stu-id="269e9-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="269e9-166">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="269e9-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="269e9-167">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="269e9-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="269e9-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="269e9-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
