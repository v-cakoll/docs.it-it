---
title: <transport> di <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 4ea60ccaba58bc0b3fa8f2263295bf1413d25e89
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399261"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="08636-102">\<> di trasporto \<di WS2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="08636-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="08636-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="08636-103">Defines authentication settings for the HTTP transport.</span></span>  
  
<span data-ttu-id="08636-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="08636-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="08636-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="08636-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="08636-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Binding >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="08636-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="08636-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> ws2007HttpBinding**](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="08636-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="08636-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding >** </span><span class="sxs-lookup"><span data-stu-id="08636-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="08636-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> di sicurezza**](security-of-ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="08636-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)</span></span>\
<span data-ttu-id="08636-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> di trasporto**</span><span class="sxs-lookup"><span data-stu-id="08636-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08636-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08636-111">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="08636-112">Type</span><span class="sxs-lookup"><span data-stu-id="08636-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08636-113">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="08636-113">Attributes and Elements</span></span>  
 <span data-ttu-id="08636-114">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="08636-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08636-115">Attributi</span><span class="sxs-lookup"><span data-stu-id="08636-115">Attributes</span></span>  
  
|<span data-ttu-id="08636-116">Attributo</span><span class="sxs-lookup"><span data-stu-id="08636-116">Attribute</span></span>|<span data-ttu-id="08636-117">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="08636-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="08636-118">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="08636-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="08636-119">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="08636-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="08636-120">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="08636-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="08636-121">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="08636-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="08636-122">L'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="08636-122">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="08636-123">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="08636-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="08636-124">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="08636-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="08636-125">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="08636-125">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="08636-126">Un utente può eseguire una query nell'area di autenticazione per determinare quale dei vari possibili nomi utente e password possono essere usati.</span><span class="sxs-lookup"><span data-stu-id="08636-126">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="08636-127">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="08636-127">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="08636-128">Value</span><span class="sxs-lookup"><span data-stu-id="08636-128">Value</span></span>|<span data-ttu-id="08636-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08636-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08636-130">Nessuna</span><span class="sxs-lookup"><span data-stu-id="08636-130">None</span></span>|<span data-ttu-id="08636-131">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="08636-131">Security is disabled.</span></span>|  
|<span data-ttu-id="08636-132">Basic</span><span class="sxs-lookup"><span data-stu-id="08636-132">Basic</span></span>|<span data-ttu-id="08636-133">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="08636-133">Uses basic authentication.</span></span>|  
|<span data-ttu-id="08636-134">Digest</span><span class="sxs-lookup"><span data-stu-id="08636-134">Digest</span></span>|<span data-ttu-id="08636-135">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="08636-135">Uses digest authentication.</span></span>|  
|<span data-ttu-id="08636-136">Ntlm</span><span class="sxs-lookup"><span data-stu-id="08636-136">Ntlm</span></span>|<span data-ttu-id="08636-137">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="08636-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="08636-138">Windows</span><span class="sxs-lookup"><span data-stu-id="08636-138">Windows</span></span>|<span data-ttu-id="08636-139">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="08636-139">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="08636-140">Certificato</span><span class="sxs-lookup"><span data-stu-id="08636-140">Certificate</span></span>|<span data-ttu-id="08636-141">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="08636-141">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="08636-142">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="08636-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="08636-143">Value</span><span class="sxs-lookup"><span data-stu-id="08636-143">Value</span></span>|<span data-ttu-id="08636-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08636-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="08636-145">Nessuna</span><span class="sxs-lookup"><span data-stu-id="08636-145">None</span></span>|<span data-ttu-id="08636-146">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="08636-146">Security is disabled.</span></span>|  
|<span data-ttu-id="08636-147">Basic</span><span class="sxs-lookup"><span data-stu-id="08636-147">Basic</span></span>|<span data-ttu-id="08636-148">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="08636-148">Uses basic authentication.</span></span>|  
|<span data-ttu-id="08636-149">Digest</span><span class="sxs-lookup"><span data-stu-id="08636-149">Digest</span></span>|<span data-ttu-id="08636-150">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="08636-150">Uses digest authentication.</span></span>|  
|<span data-ttu-id="08636-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="08636-151">Ntlm</span></span>|<span data-ttu-id="08636-152">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="08636-152">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="08636-153">Windows</span><span class="sxs-lookup"><span data-stu-id="08636-153">Windows</span></span>|<span data-ttu-id="08636-154">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="08636-154">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="08636-155">Certificato</span><span class="sxs-lookup"><span data-stu-id="08636-155">Certificate</span></span>|<span data-ttu-id="08636-156">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="08636-156">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08636-157">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="08636-157">Child Elements</span></span>  
 <span data-ttu-id="08636-158">Nessuna</span><span class="sxs-lookup"><span data-stu-id="08636-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08636-159">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="08636-159">Parent Elements</span></span>  
  
|<span data-ttu-id="08636-160">Elemento</span><span class="sxs-lookup"><span data-stu-id="08636-160">Element</span></span>|<span data-ttu-id="08636-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08636-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08636-162">\<security></span><span class="sxs-lookup"><span data-stu-id="08636-162">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="08636-163">Rappresenta le funzionalità di sicurezza dell' [ \<elemento > WS2007HttpBinding](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="08636-163">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08636-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08636-164">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="08636-165">Protezione di servizi e client</span><span class="sxs-lookup"><span data-stu-id="08636-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="08636-166">Associazioni</span><span class="sxs-lookup"><span data-stu-id="08636-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="08636-167">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="08636-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="08636-168">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="08636-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="08636-169">\<binding></span><span class="sxs-lookup"><span data-stu-id="08636-169">\<binding></span></span>](../../../misc/binding.md)
