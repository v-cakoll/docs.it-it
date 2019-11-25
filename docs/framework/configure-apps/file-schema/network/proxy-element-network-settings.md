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
ms.openlocfilehash: 5f327a2bb4fe316497614f14669907d514c20654
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089187"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="2f051-102">\<elemento > proxy (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2f051-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="2f051-103">Definisce un server proxy.</span><span class="sxs-lookup"><span data-stu-id="2f051-103">Defines a proxy server.</span></span>  

<span data-ttu-id="2f051-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2f051-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2f051-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2f051-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="2f051-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy**](defaultproxy-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="2f051-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)</span></span>\
<span data-ttu-id="2f051-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**proxy** ></span><span class="sxs-lookup"><span data-stu-id="2f051-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2f051-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f051-108">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f051-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2f051-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2f051-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2f051-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f051-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="2f051-111">Attributes</span></span>  
  
|<span data-ttu-id="2f051-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="2f051-112">**Attribute**</span></span>|<span data-ttu-id="2f051-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2f051-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="2f051-114">Specifica se il proxy viene rilevato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2f051-114">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="2f051-115">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="2f051-115">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="2f051-116">Specifica se il proxy viene ignorato per le risorse locali.</span><span class="sxs-lookup"><span data-stu-id="2f051-116">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="2f051-117">Le risorse locali includono il server locale (`http://localhost`, `http://loopback`o `http://127.0.0.1`) e un URI senza un punto (`http://webserver`).</span><span class="sxs-lookup"><span data-stu-id="2f051-117">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="2f051-118">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="2f051-118">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="2f051-119">Specifica l'URI del proxy da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2f051-119">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="2f051-120">Specifica il percorso dello script di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2f051-120">Specifies the location of the configuration script.</span></span> <span data-ttu-id="2f051-121">Non usare l'attributo `bypassonlocal` con questo attributo.</span><span class="sxs-lookup"><span data-stu-id="2f051-121">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="2f051-122">Specifica se utilizzare le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2f051-122">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="2f051-123">Se impostato su `true`, gli attributi successivi sostituiranno le impostazioni proxy di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2f051-123">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="2f051-124">Il valore predefinito è `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="2f051-124">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f051-125">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2f051-125">Child Elements</span></span>  
 <span data-ttu-id="2f051-126">Nessuna.</span><span class="sxs-lookup"><span data-stu-id="2f051-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f051-127">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2f051-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2f051-128">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="2f051-128">**Element**</span></span>|<span data-ttu-id="2f051-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2f051-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2f051-130">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2f051-130">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="2f051-131">Configura il server proxy Hypertext Transfer Protocol (HTTP).</span><span class="sxs-lookup"><span data-stu-id="2f051-131">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="2f051-132">Valore di testo</span><span class="sxs-lookup"><span data-stu-id="2f051-132">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f051-133">Note</span><span class="sxs-lookup"><span data-stu-id="2f051-133">Remarks</span></span>  
 <span data-ttu-id="2f051-134">L'elemento `proxy` definisce un server proxy per un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2f051-134">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="2f051-135">Se questo elemento non è presente nel file di configurazione, il .NET Framework utilizzerà le impostazioni del proxy in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2f051-135">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="2f051-136">Il valore per l'attributo `proxyaddress` deve essere un URI (Uniform Resource Indicator) ben formato.</span><span class="sxs-lookup"><span data-stu-id="2f051-136">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="2f051-137">L'attributo `scriptLocation` si riferisce al rilevamento automatico degli script di configurazione del proxy.</span><span class="sxs-lookup"><span data-stu-id="2f051-137">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="2f051-138">La classe <xref:System.Net.WebProxy> tenterà di individuare uno script di configurazione, in genere denominato wpad. dat, quando si seleziona l'opzione **Usa script di configurazione automatica** in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2f051-138">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="2f051-139">Se `bypassonlocal` è impostato su un valore qualsiasi, `scriptLocation` viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="2f051-139">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="2f051-140">Usare l'attributo `usesystemdefault` per le applicazioni .NET Framework versione 1,1 che eseguono la migrazione alla versione 2,0.</span><span class="sxs-lookup"><span data-stu-id="2f051-140">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="2f051-141">Viene generata un'eccezione se l'attributo `proxyaddress` specifica un proxy predefinito non valido.</span><span class="sxs-lookup"><span data-stu-id="2f051-141">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="2f051-142">La proprietà <xref:System.Exception.InnerException%2A> nell'eccezione dovrebbe contenere altre informazioni sulla causa radice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="2f051-142">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2f051-143">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="2f051-143">Configuration Files</span></span>  
 <span data-ttu-id="2f051-144">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="2f051-144">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f051-145">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f051-145">Example</span></span>  
 <span data-ttu-id="2f051-146">Nell'esempio seguente vengono utilizzate le impostazioni predefinite del proxy di Internet Explorer, viene specificato l'indirizzo proxy e viene ignorato il proxy per l'accesso locale.</span><span class="sxs-lookup"><span data-stu-id="2f051-146">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f051-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f051-147">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="2f051-148">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="2f051-148">Network Settings Schema</span></span>](index.md)
