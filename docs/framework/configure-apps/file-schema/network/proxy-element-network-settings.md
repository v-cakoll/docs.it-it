---
title: Elemento <proxy> (impostazioni di rete)
description: L' <proxy> elemento impostazioni di rete definisce le opzioni del server proxy nel .NET Framework. Questo articolo include un esempio.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 0d462fcc92fc1be5ddbc2e76237d8436219c7295
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504537"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="97ed2-104">Elemento \<proxy> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="97ed2-104">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="97ed2-105">Definisce un server proxy.</span><span class="sxs-lookup"><span data-stu-id="97ed2-105">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="97ed2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97ed2-106">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97ed2-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="97ed2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="97ed2-108">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="97ed2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97ed2-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="97ed2-109">Attributes</span></span>  
  
|<span data-ttu-id="97ed2-110">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="97ed2-110">**Attribute**</span></span>|<span data-ttu-id="97ed2-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="97ed2-111">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="97ed2-112">Specifica se il proxy viene rilevato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="97ed2-112">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="97ed2-113">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="97ed2-113">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="97ed2-114">Specifica se il proxy viene ignorato per le risorse locali.</span><span class="sxs-lookup"><span data-stu-id="97ed2-114">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="97ed2-115">Le risorse locali includono il server locale ( `http://localhost` , `http://loopback` o `http://127.0.0.1` ) e un URI senza un punto ( `http://webserver` ).</span><span class="sxs-lookup"><span data-stu-id="97ed2-115">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="97ed2-116">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="97ed2-116">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="97ed2-117">Specifica l'URI del proxy da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="97ed2-117">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="97ed2-118">Specifica il percorso dello script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="97ed2-118">Specifies the location of the configuration script.</span></span> <span data-ttu-id="97ed2-119">Non usare l' `bypassonlocal` attributo con questo attributo.</span><span class="sxs-lookup"><span data-stu-id="97ed2-119">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="97ed2-120">Specifica se utilizzare le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="97ed2-120">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="97ed2-121">Se è impostato su `true` , gli attributi successivi sostituiranno le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="97ed2-121">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="97ed2-122">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="97ed2-122">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97ed2-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="97ed2-123">Child Elements</span></span>  
 <span data-ttu-id="97ed2-124">No.</span><span class="sxs-lookup"><span data-stu-id="97ed2-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97ed2-125">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="97ed2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="97ed2-126">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="97ed2-126">**Element**</span></span>|<span data-ttu-id="97ed2-127">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="97ed2-127">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="97ed2-128">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="97ed2-128">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="97ed2-129">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="97ed2-129">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="97ed2-130">Valore di testo</span><span class="sxs-lookup"><span data-stu-id="97ed2-130">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97ed2-131">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="97ed2-131">Remarks</span></span>  
 <span data-ttu-id="97ed2-132">L' `proxy` elemento definisce un server proxy per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97ed2-132">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="97ed2-133">Se questo elemento non è presente nel file di configurazione, il .NET Framework utilizzerà le impostazioni del proxy in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="97ed2-133">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="97ed2-134">Il valore dell' `proxyaddress` attributo deve essere un URI (Uniform Resource Indicator) ben formato.</span><span class="sxs-lookup"><span data-stu-id="97ed2-134">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="97ed2-135">L' `scriptLocation` attributo fa riferimento al rilevamento automatico degli script di configurazione del proxy.</span><span class="sxs-lookup"><span data-stu-id="97ed2-135">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="97ed2-136">La <xref:System.Net.WebProxy> classe tenterà di individuare uno script di configurazione, in genere denominato wpad. dat, quando si seleziona l'opzione **Usa script di configurazione automatica** in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="97ed2-136">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="97ed2-137">Se `bypassonlocal` è impostato su un valore qualsiasi, `scriptLocation` viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="97ed2-137">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="97ed2-138">Usare l' `usesystemdefault` attributo per .NET Framework versione 1,1 applicazioni che eseguono la migrazione alla versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="97ed2-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="97ed2-139">Viene generata un'eccezione se l' `proxyaddress` attributo specifica un proxy predefinito non valido.</span><span class="sxs-lookup"><span data-stu-id="97ed2-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="97ed2-140">La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa radice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="97ed2-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="97ed2-141">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="97ed2-141">Configuration Files</span></span>  
 <span data-ttu-id="97ed2-142">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="97ed2-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="97ed2-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="97ed2-143">Example</span></span>  
 <span data-ttu-id="97ed2-144">Nell'esempio seguente vengono utilizzate le impostazioni predefinite del proxy di Internet Explorer, viene specificato l'indirizzo proxy e viene ignorato il proxy per l'accesso locale.</span><span class="sxs-lookup"><span data-stu-id="97ed2-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97ed2-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97ed2-145">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="97ed2-146">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="97ed2-146">Network Settings Schema</span></span>](index.md)
