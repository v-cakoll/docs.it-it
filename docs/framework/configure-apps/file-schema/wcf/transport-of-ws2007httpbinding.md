---
title: '&lt;transport&gt; di &lt;ws2007HttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc60e72ae810578edb71b73b39e756a951b1f425
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="d426f-102">&lt;transport&gt; di &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="d426f-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="d426f-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="d426f-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="d426f-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d426f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d426f-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="d426f-105">\<bindings></span></span>  
<span data-ttu-id="d426f-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d426f-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="d426f-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="d426f-107">\<binding></span></span>  
<span data-ttu-id="d426f-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="d426f-108">\<security></span></span>  
<span data-ttu-id="d426f-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="d426f-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d426f-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d426f-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="d426f-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="d426f-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d426f-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d426f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d426f-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d426f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d426f-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="d426f-114">Attributes</span></span>  
  
|<span data-ttu-id="d426f-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="d426f-115">Attribute</span></span>|<span data-ttu-id="d426f-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d426f-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="d426f-117">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="d426f-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="d426f-118">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d426f-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="d426f-119">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="d426f-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="d426f-120">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d426f-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="d426f-121">L'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="d426f-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="d426f-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="d426f-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="d426f-123">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d426f-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="d426f-124">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="d426f-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="d426f-125">Un utente può eseguire una query nell'area di autenticazione per determinare quale dei vari possibili nomi utente e password possono essere usati.</span><span class="sxs-lookup"><span data-stu-id="d426f-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="d426f-126">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d426f-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="d426f-127">Valore</span><span class="sxs-lookup"><span data-stu-id="d426f-127">Value</span></span>|<span data-ttu-id="d426f-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d426f-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d426f-129">None</span><span class="sxs-lookup"><span data-stu-id="d426f-129">None</span></span>|<span data-ttu-id="d426f-130">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d426f-130">Security is disabled.</span></span>|  
|<span data-ttu-id="d426f-131">Di base</span><span class="sxs-lookup"><span data-stu-id="d426f-131">Basic</span></span>|<span data-ttu-id="d426f-132">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="d426f-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="d426f-133">Digest</span><span class="sxs-lookup"><span data-stu-id="d426f-133">Digest</span></span>|<span data-ttu-id="d426f-134">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="d426f-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="d426f-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="d426f-135">Ntlm</span></span>|<span data-ttu-id="d426f-136">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="d426f-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="d426f-137">Windows</span><span class="sxs-lookup"><span data-stu-id="d426f-137">Windows</span></span>|<span data-ttu-id="d426f-138">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="d426f-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="d426f-139">Certificato</span><span class="sxs-lookup"><span data-stu-id="d426f-139">Certificate</span></span>|<span data-ttu-id="d426f-140">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="d426f-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="d426f-141">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="d426f-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="d426f-142">Valore</span><span class="sxs-lookup"><span data-stu-id="d426f-142">Value</span></span>|<span data-ttu-id="d426f-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d426f-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d426f-144">None</span><span class="sxs-lookup"><span data-stu-id="d426f-144">None</span></span>|<span data-ttu-id="d426f-145">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d426f-145">Security is disabled.</span></span>|  
|<span data-ttu-id="d426f-146">Di base</span><span class="sxs-lookup"><span data-stu-id="d426f-146">Basic</span></span>|<span data-ttu-id="d426f-147">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="d426f-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="d426f-148">Digest</span><span class="sxs-lookup"><span data-stu-id="d426f-148">Digest</span></span>|<span data-ttu-id="d426f-149">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="d426f-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="d426f-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="d426f-150">Ntlm</span></span>|<span data-ttu-id="d426f-151">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="d426f-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="d426f-152">Windows</span><span class="sxs-lookup"><span data-stu-id="d426f-152">Windows</span></span>|<span data-ttu-id="d426f-153">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="d426f-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="d426f-154">Certificato</span><span class="sxs-lookup"><span data-stu-id="d426f-154">Certificate</span></span>|<span data-ttu-id="d426f-155">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="d426f-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d426f-156">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d426f-156">Child Elements</span></span>  
 <span data-ttu-id="d426f-157">None</span><span class="sxs-lookup"><span data-stu-id="d426f-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d426f-158">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d426f-158">Parent Elements</span></span>  
  
|<span data-ttu-id="d426f-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="d426f-159">Element</span></span>|<span data-ttu-id="d426f-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d426f-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d426f-161">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="d426f-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="d426f-162">Rappresenta le funzionalità di sicurezza di [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d426f-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d426f-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d426f-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="d426f-164">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="d426f-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="d426f-165">Associazioni</span><span class="sxs-lookup"><span data-stu-id="d426f-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d426f-166">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="d426f-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="d426f-167">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d426f-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="d426f-168">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="d426f-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
