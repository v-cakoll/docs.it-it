---
title: '&lt;proxy&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b0b397e66e0f73d10f482bc9151a6fbacf3e774d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltproxygt-element-network-settings"></a><span data-ttu-id="837ab-102">&lt;proxy&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="837ab-102">&lt;proxy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="837ab-103">Definisce un server proxy.</span><span class="sxs-lookup"><span data-stu-id="837ab-103">Defines a proxy server.</span></span>  
  
 <span data-ttu-id="837ab-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="837ab-104">\<configuration></span></span>  
<span data-ttu-id="837ab-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="837ab-105">\<system.net></span></span>  
<span data-ttu-id="837ab-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="837ab-106">\<defaultProxy></span></span>  
<span data-ttu-id="837ab-107">\<proxy ></span><span class="sxs-lookup"><span data-stu-id="837ab-107">\<proxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="837ab-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="837ab-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="837ab-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="837ab-109">Attributes and Elements</span></span>  
 <span data-ttu-id="837ab-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="837ab-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="837ab-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="837ab-111">Attributes</span></span>  
  
|<span data-ttu-id="837ab-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="837ab-112">**Attribute**</span></span>|<span data-ttu-id="837ab-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="837ab-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="837ab-114">Specifica se il proxy viene rilevato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="837ab-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="837ab-115">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="837ab-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="837ab-116">Specifica se il proxy viene ignorato per le risorse locali.</span><span class="sxs-lookup"><span data-stu-id="837ab-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="837ab-117">Le risorse locali includono il server locale (http://localhost, http://loopback o http://127.0.0.1) e un URI senza punto (http://webserver).</span><span class="sxs-lookup"><span data-stu-id="837ab-117">Local resources include the local server (http://localhost, http://loopback, or http://127.0.0.1) and a URI without a period (http://webserver).</span></span> <span data-ttu-id="837ab-118">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="837ab-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="837ab-119">Specifica l'URI del proxy da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="837ab-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="837ab-120">Specifica il percorso dello script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="837ab-120">Specifies the location of the configuration script.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="837ab-121">Specifica se utilizzare le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="837ab-121">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="837ab-122">Se impostato su `true`, gli attributi successivi sostituiranno le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="837ab-122">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="837ab-123">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="837ab-123">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="837ab-124">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="837ab-124">Child Elements</span></span>  
 <span data-ttu-id="837ab-125">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="837ab-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="837ab-126">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="837ab-126">Parent Elements</span></span>  
  
|<span data-ttu-id="837ab-127">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="837ab-127">**Element**</span></span>|<span data-ttu-id="837ab-128">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="837ab-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="837ab-129">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="837ab-129">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="837ab-130">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="837ab-130">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="837ab-131">Valore di testo</span><span class="sxs-lookup"><span data-stu-id="837ab-131">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="837ab-132">Note</span><span class="sxs-lookup"><span data-stu-id="837ab-132">Remarks</span></span>  
 <span data-ttu-id="837ab-133">Il `proxy` elemento definisce un server proxy per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="837ab-133">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="837ab-134">Se questo elemento è mancano dal file di configurazione, .NET Framework utilizzerà le impostazioni del proxy in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="837ab-134">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="837ab-135">Il valore per il `proxyaddress` attributo deve essere un formato corretto indicatore URI (Uniform Resource).</span><span class="sxs-lookup"><span data-stu-id="837ab-135">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="837ab-136">Il `scriptLocation` attributo fa riferimento per il rilevamento automatico proxy script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="837ab-136">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="837ab-137">Il <xref:System.Net.WebProxy> classe tenterà di individuare uno script di configurazione (in genere denominato WPAD) quando il **utilizzare script di configurazione automatica** opzione è selezionata in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="837ab-137">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span>  
  
 <span data-ttu-id="837ab-138">Utilizzare il `usesystemdefault` attributo per le applicazioni .NET Framework versione 1.1 che esegue la migrazione alla versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="837ab-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="837ab-139">Viene generata un'eccezione se il `proxyaddress` attributo specifica un proxy predefinito non valido.</span><span class="sxs-lookup"><span data-stu-id="837ab-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="837ab-140">La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa principale dell'errore.</span><span class="sxs-lookup"><span data-stu-id="837ab-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="837ab-141">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="837ab-141">Configuration Files</span></span>  
 <span data-ttu-id="837ab-142">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="837ab-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="837ab-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="837ab-143">Example</span></span>  
 <span data-ttu-id="837ab-144">Nell'esempio seguente usa le impostazioni predefinite del proxy di Internet Explorer, specifica l'indirizzo del proxy e ignora il proxy per l'accesso locale.</span><span class="sxs-lookup"><span data-stu-id="837ab-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="837ab-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="837ab-145">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="837ab-146">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="837ab-146">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
