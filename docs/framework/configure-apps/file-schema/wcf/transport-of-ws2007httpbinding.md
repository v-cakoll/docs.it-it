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
ms.openlocfilehash: 573b7fb5cf130d0a638326b87ae49f90db881df4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="9e82e-102">&lt;transport&gt; di &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="9e82e-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="9e82e-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="9e82e-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="9e82e-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9e82e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9e82e-105">\<associazioni ></span><span class="sxs-lookup"><span data-stu-id="9e82e-105">\<bindings></span></span>  
<span data-ttu-id="9e82e-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9e82e-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="9e82e-107">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="9e82e-107">\<binding></span></span>  
<span data-ttu-id="9e82e-108">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="9e82e-108">\<security></span></span>  
<span data-ttu-id="9e82e-109">\<trasporto ></span><span class="sxs-lookup"><span data-stu-id="9e82e-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e82e-110">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e82e-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="9e82e-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="9e82e-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e82e-112">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9e82e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9e82e-113">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9e82e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e82e-114">Attributi</span><span class="sxs-lookup"><span data-stu-id="9e82e-114">Attributes</span></span>  
  
|<span data-ttu-id="9e82e-115">Attributo</span><span class="sxs-lookup"><span data-stu-id="9e82e-115">Attribute</span></span>|<span data-ttu-id="9e82e-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e82e-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="9e82e-117">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="9e82e-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="9e82e-118">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9e82e-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="9e82e-119">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="9e82e-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="9e82e-120">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9e82e-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="9e82e-121">L'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="9e82e-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="9e82e-122">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="9e82e-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="9e82e-123">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="9e82e-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="9e82e-124">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="9e82e-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="9e82e-125">Un utente può eseguire una query nell'area di autenticazione per determinare quale dei vari possibili nomi utente e password possono essere usati.</span><span class="sxs-lookup"><span data-stu-id="9e82e-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="9e82e-126">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9e82e-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9e82e-127">Valore</span><span class="sxs-lookup"><span data-stu-id="9e82e-127">Value</span></span>|<span data-ttu-id="9e82e-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e82e-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9e82e-129">None</span><span class="sxs-lookup"><span data-stu-id="9e82e-129">None</span></span>|<span data-ttu-id="9e82e-130">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="9e82e-130">Security is disabled.</span></span>|  
|<span data-ttu-id="9e82e-131">Di base</span><span class="sxs-lookup"><span data-stu-id="9e82e-131">Basic</span></span>|<span data-ttu-id="9e82e-132">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="9e82e-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="9e82e-133">Digest</span><span class="sxs-lookup"><span data-stu-id="9e82e-133">Digest</span></span>|<span data-ttu-id="9e82e-134">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="9e82e-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="9e82e-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="9e82e-135">Ntlm</span></span>|<span data-ttu-id="9e82e-136">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="9e82e-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="9e82e-137">Windows</span><span class="sxs-lookup"><span data-stu-id="9e82e-137">Windows</span></span>|<span data-ttu-id="9e82e-138">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="9e82e-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="9e82e-139">Certificato</span><span class="sxs-lookup"><span data-stu-id="9e82e-139">Certificate</span></span>|<span data-ttu-id="9e82e-140">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="9e82e-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="9e82e-141">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="9e82e-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="9e82e-142">Valore</span><span class="sxs-lookup"><span data-stu-id="9e82e-142">Value</span></span>|<span data-ttu-id="9e82e-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e82e-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9e82e-144">None</span><span class="sxs-lookup"><span data-stu-id="9e82e-144">None</span></span>|<span data-ttu-id="9e82e-145">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="9e82e-145">Security is disabled.</span></span>|  
|<span data-ttu-id="9e82e-146">Di base</span><span class="sxs-lookup"><span data-stu-id="9e82e-146">Basic</span></span>|<span data-ttu-id="9e82e-147">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="9e82e-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="9e82e-148">Digest</span><span class="sxs-lookup"><span data-stu-id="9e82e-148">Digest</span></span>|<span data-ttu-id="9e82e-149">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="9e82e-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="9e82e-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="9e82e-150">Ntlm</span></span>|<span data-ttu-id="9e82e-151">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="9e82e-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="9e82e-152">Windows</span><span class="sxs-lookup"><span data-stu-id="9e82e-152">Windows</span></span>|<span data-ttu-id="9e82e-153">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="9e82e-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="9e82e-154">Certificato</span><span class="sxs-lookup"><span data-stu-id="9e82e-154">Certificate</span></span>|<span data-ttu-id="9e82e-155">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="9e82e-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e82e-156">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9e82e-156">Child Elements</span></span>  
 <span data-ttu-id="9e82e-157">None</span><span class="sxs-lookup"><span data-stu-id="9e82e-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e82e-158">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9e82e-158">Parent Elements</span></span>  
  
|<span data-ttu-id="9e82e-159">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e82e-159">Element</span></span>|<span data-ttu-id="9e82e-160">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e82e-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e82e-161">\<sicurezza ></span><span class="sxs-lookup"><span data-stu-id="9e82e-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="9e82e-162">Rappresenta le funzionalità di sicurezza di [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="9e82e-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e82e-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e82e-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="9e82e-164">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="9e82e-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9e82e-165">Associazioni</span><span class="sxs-lookup"><span data-stu-id="9e82e-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9e82e-166">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="9e82e-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9e82e-167">Uso di associazioni per configurare i client e servizi Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9e82e-167">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9e82e-168">\<associazione ></span><span class="sxs-lookup"><span data-stu-id="9e82e-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
