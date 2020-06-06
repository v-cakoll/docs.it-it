---
title: <transport> di <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732771"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="caa18-102">\<transport> di \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="caa18-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="caa18-103">Definisce le impostazioni di autenticazione per il trasporto HTTP.</span><span class="sxs-lookup"><span data-stu-id="caa18-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="caa18-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="caa18-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="caa18-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="caa18-105">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="caa18-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="caa18-106">Attributes and Elements</span></span>  
 <span data-ttu-id="caa18-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="caa18-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="caa18-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="caa18-108">Attributes</span></span>  
  
|<span data-ttu-id="caa18-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="caa18-109">Attribute</span></span>|<span data-ttu-id="caa18-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="caa18-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="caa18-111">Specifica la credenziale usata per autenticare il client presso il servizio.</span><span class="sxs-lookup"><span data-stu-id="caa18-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="caa18-112">L'attributo è di tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="caa18-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="caa18-113">Specifica la credenziale usata per autenticare il client presso un proxy di dominio.</span><span class="sxs-lookup"><span data-stu-id="caa18-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="caa18-114">L'attributo è di tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="caa18-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="caa18-115">L'area di autenticazione per l'autenticazione di base o digest.</span><span class="sxs-lookup"><span data-stu-id="caa18-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="caa18-116">Il valore predefinito è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="caa18-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="caa18-117">L'area di autenticazione specifica almeno il nome dell'host che esegue l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="caa18-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="caa18-118">Può inoltre specificare una raccolta di utenti aventi diritto di accesso.</span><span class="sxs-lookup"><span data-stu-id="caa18-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="caa18-119">Un utente può eseguire una query nell'area di autenticazione per determinare quale dei vari possibili nomi utente e password possono essere usati.</span><span class="sxs-lookup"><span data-stu-id="caa18-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="caa18-120">Attributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="caa18-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="caa18-121">Valore</span><span class="sxs-lookup"><span data-stu-id="caa18-121">Value</span></span>|<span data-ttu-id="caa18-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="caa18-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="caa18-123">nessuno</span><span class="sxs-lookup"><span data-stu-id="caa18-123">None</span></span>|<span data-ttu-id="caa18-124">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="caa18-124">Security is disabled.</span></span>|  
|<span data-ttu-id="caa18-125">Basic</span><span class="sxs-lookup"><span data-stu-id="caa18-125">Basic</span></span>|<span data-ttu-id="caa18-126">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="caa18-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="caa18-127">Digest</span><span class="sxs-lookup"><span data-stu-id="caa18-127">Digest</span></span>|<span data-ttu-id="caa18-128">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="caa18-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="caa18-129">NTLM</span><span class="sxs-lookup"><span data-stu-id="caa18-129">Ntlm</span></span>|<span data-ttu-id="caa18-130">Usa l'autenticazione NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="caa18-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="caa18-131">Windows</span><span class="sxs-lookup"><span data-stu-id="caa18-131">Windows</span></span>|<span data-ttu-id="caa18-132">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="caa18-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="caa18-133">Certificato</span><span class="sxs-lookup"><span data-stu-id="caa18-133">Certificate</span></span>|<span data-ttu-id="caa18-134">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="caa18-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="caa18-135">Attributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="caa18-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="caa18-136">Valore</span><span class="sxs-lookup"><span data-stu-id="caa18-136">Value</span></span>|<span data-ttu-id="caa18-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="caa18-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="caa18-138">nessuno</span><span class="sxs-lookup"><span data-stu-id="caa18-138">None</span></span>|<span data-ttu-id="caa18-139">La sicurezza è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="caa18-139">Security is disabled.</span></span>|  
|<span data-ttu-id="caa18-140">Basic</span><span class="sxs-lookup"><span data-stu-id="caa18-140">Basic</span></span>|<span data-ttu-id="caa18-141">Usa l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="caa18-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="caa18-142">Digest</span><span class="sxs-lookup"><span data-stu-id="caa18-142">Digest</span></span>|<span data-ttu-id="caa18-143">Usa l'autenticazione digest.</span><span class="sxs-lookup"><span data-stu-id="caa18-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="caa18-144">NTLM</span><span class="sxs-lookup"><span data-stu-id="caa18-144">Ntlm</span></span>|<span data-ttu-id="caa18-145">Usa NTLM come fallback con un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="caa18-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="caa18-146">Windows</span><span class="sxs-lookup"><span data-stu-id="caa18-146">Windows</span></span>|<span data-ttu-id="caa18-147">Usa l'autenticazione integrata di Windows.</span><span class="sxs-lookup"><span data-stu-id="caa18-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="caa18-148">Certificato</span><span class="sxs-lookup"><span data-stu-id="caa18-148">Certificate</span></span>|<span data-ttu-id="caa18-149">Usa certificati X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="caa18-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="caa18-150">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="caa18-150">Child Elements</span></span>  
 <span data-ttu-id="caa18-151">nessuno</span><span class="sxs-lookup"><span data-stu-id="caa18-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="caa18-152">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="caa18-152">Parent Elements</span></span>  
  
|<span data-ttu-id="caa18-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="caa18-153">Element</span></span>|<span data-ttu-id="caa18-154">Descrizione</span><span class="sxs-lookup"><span data-stu-id="caa18-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="caa18-155">Rappresenta le funzionalità di sicurezza dell' [\<ws2007HttpBinding>](ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="caa18-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="caa18-156">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="caa18-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="caa18-157">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="caa18-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="caa18-158">Binding</span><span class="sxs-lookup"><span data-stu-id="caa18-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="caa18-159">Configurazione di associazioni fornite dal sistema</span><span class="sxs-lookup"><span data-stu-id="caa18-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="caa18-160">Uso di associazioni per configurare servizi e client</span><span class="sxs-lookup"><span data-stu-id="caa18-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
