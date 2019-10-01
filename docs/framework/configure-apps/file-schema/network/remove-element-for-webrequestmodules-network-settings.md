---
title: Elemento <remove> per webRequestModules (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
ms.openlocfilehash: f8209ea89ac8cd214389feddee8c475e10bc939a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697811"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="a6262-102">Elemento > \<remove per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="a6262-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="a6262-103">Rimuove un modulo di richiesta Web personalizzato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a6262-103">Removes a custom Web request module from the application.</span></span>  
  
[<span data-ttu-id="a6262-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a6262-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="a6262-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a6262-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="a6262-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a6262-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="a6262-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="a6262-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6262-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6262-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6262-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a6262-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a6262-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a6262-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6262-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="a6262-111">Attributes</span></span>  
  
|<span data-ttu-id="a6262-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="a6262-112">**Attribute**</span></span>|<span data-ttu-id="a6262-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a6262-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="a6262-114">Prefisso URI per le richieste gestite da questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="a6262-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6262-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a6262-115">Child Elements</span></span>  
 <span data-ttu-id="a6262-116">No.</span><span class="sxs-lookup"><span data-stu-id="a6262-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6262-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a6262-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a6262-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a6262-118">**Element**</span></span>|<span data-ttu-id="a6262-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a6262-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a6262-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="a6262-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="a6262-121">Specifica i moduli da usare per richiedere informazioni dagli host di rete.</span><span class="sxs-lookup"><span data-stu-id="a6262-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6262-122">Note</span><span class="sxs-lookup"><span data-stu-id="a6262-122">Remarks</span></span>  
 <span data-ttu-id="a6262-123">L'elemento `remove` rimuove il modulo di richiesta Web registrato per il prefisso URI specificato.</span><span class="sxs-lookup"><span data-stu-id="a6262-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="a6262-124">Il valore dell'attributo `prefix` deve essere costituito dai caratteri iniziali di un URI valido, ad esempio "`http`" o "`http://www.contoso.com`".</span><span class="sxs-lookup"><span data-stu-id="a6262-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a6262-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="a6262-125">Configuration Files</span></span>  
 <span data-ttu-id="a6262-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a6262-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6262-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="a6262-127">Example</span></span>  

<span data-ttu-id="a6262-128">Nell'esempio seguente viene rimosso il modulo di richiesta Web esistente per HTTP, quindi viene registrato un nuovo modulo di richiesta Web personalizzato per le richieste HTTP a `www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="a6262-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6262-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6262-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="a6262-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="a6262-130">Network Settings Schema</span></span>](index.md)
