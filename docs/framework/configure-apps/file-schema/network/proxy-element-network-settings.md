---
title: Elemento <proxy> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154790"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="ea7dc-102">Elemento \<proxy> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ea7dc-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="ea7dc-103">Definisce un server proxy.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-103">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="ea7dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea7dc-104">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea7dc-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ea7dc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ea7dc-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea7dc-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="ea7dc-107">Attributes</span></span>  
  
|<span data-ttu-id="ea7dc-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="ea7dc-108">**Attribute**</span></span>|<span data-ttu-id="ea7dc-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ea7dc-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="ea7dc-110">Specifica se il proxy viene rilevato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-110">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="ea7dc-111">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-111">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="ea7dc-112">Specifica se il proxy viene ignorato per le risorse locali.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-112">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="ea7dc-113">Le risorse locali includono il server locale ( `http://localhost` , `http://loopback` o `http://127.0.0.1` ) e un URI senza un punto ( `http://webserver` ).</span><span class="sxs-lookup"><span data-stu-id="ea7dc-113">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="ea7dc-114">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-114">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="ea7dc-115">Specifica l'URI del proxy da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-115">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="ea7dc-116">Specifica il percorso dello script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-116">Specifies the location of the configuration script.</span></span> <span data-ttu-id="ea7dc-117">Non usare l' `bypassonlocal` attributo con questo attributo.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-117">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="ea7dc-118">Specifica se utilizzare le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-118">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="ea7dc-119">Se è impostato su `true` , gli attributi successivi sostituiranno le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-119">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="ea7dc-120">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-120">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea7dc-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ea7dc-121">Child Elements</span></span>  
 <span data-ttu-id="ea7dc-122">No.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea7dc-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ea7dc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ea7dc-124">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ea7dc-124">**Element**</span></span>|<span data-ttu-id="ea7dc-125">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ea7dc-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ea7dc-126">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="ea7dc-126">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="ea7dc-127">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="ea7dc-127">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="ea7dc-128">Valore di testo</span><span class="sxs-lookup"><span data-stu-id="ea7dc-128">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea7dc-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="ea7dc-129">Remarks</span></span>  
 <span data-ttu-id="ea7dc-130">L' `proxy` elemento definisce un server proxy per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-130">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="ea7dc-131">Se questo elemento non è presente nel file di configurazione, il .NET Framework utilizzerà le impostazioni del proxy in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-131">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="ea7dc-132">Il valore dell' `proxyaddress` attributo deve essere un URI (Uniform Resource Indicator) ben formato.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-132">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="ea7dc-133">L' `scriptLocation` attributo fa riferimento al rilevamento automatico degli script di configurazione del proxy.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-133">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="ea7dc-134">La <xref:System.Net.WebProxy> classe tenterà di individuare uno script di configurazione, in genere denominato wpad. dat, quando si seleziona l'opzione **Usa script di configurazione automatica** in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-134">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="ea7dc-135">Se `bypassonlocal` è impostato su un valore qualsiasi, `scriptLocation` viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-135">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="ea7dc-136">Usare l' `usesystemdefault` attributo per .NET Framework versione 1,1 applicazioni che eseguono la migrazione alla versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-136">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="ea7dc-137">Viene generata un'eccezione se l' `proxyaddress` attributo specifica un proxy predefinito non valido.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-137">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="ea7dc-138">La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa radice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-138">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ea7dc-139">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ea7dc-139">Configuration Files</span></span>  
 <span data-ttu-id="ea7dc-140">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ea7dc-140">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea7dc-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="ea7dc-141">Example</span></span>  
 <span data-ttu-id="ea7dc-142">Nell'esempio seguente vengono utilizzate le impostazioni predefinite del proxy di Internet Explorer, viene specificato l'indirizzo proxy e viene ignorato il proxy per l'accesso locale.</span><span class="sxs-lookup"><span data-stu-id="ea7dc-142">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ea7dc-143">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ea7dc-143">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="ea7dc-144">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ea7dc-144">Network Settings Schema</span></span>](index.md)
