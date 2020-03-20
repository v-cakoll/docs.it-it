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
ms.openlocfilehash: afa1aef8ea71f43a136987ec5b6e1925c6d9fb40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154725"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="0adf5-102">\<rimuovere>elemento per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="0adf5-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="0adf5-103">Rimuove un modulo di richiesta Web personalizzato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0adf5-103">Removes a custom Web request module from the application.</span></span>  
  
<span data-ttu-id="0adf5-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0adf5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0adf5-105">&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0adf5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="0adf5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>webRequestModules**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0adf5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="0adf5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rimuovere>**</span><span class="sxs-lookup"><span data-stu-id="0adf5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="0adf5-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0adf5-108">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0adf5-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0adf5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0adf5-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0adf5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0adf5-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="0adf5-111">Attributes</span></span>  
  
|<span data-ttu-id="0adf5-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="0adf5-112">**Attribute**</span></span>|<span data-ttu-id="0adf5-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0adf5-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="0adf5-114">Prefisso URI per le richieste gestite da questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="0adf5-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0adf5-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0adf5-115">Child Elements</span></span>  
 <span data-ttu-id="0adf5-116">No.</span><span class="sxs-lookup"><span data-stu-id="0adf5-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0adf5-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0adf5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0adf5-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="0adf5-118">**Element**</span></span>|<span data-ttu-id="0adf5-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0adf5-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0adf5-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="0adf5-120">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="0adf5-121">Specifica i moduli da utilizzare per richiedere informazioni agli host di rete.</span><span class="sxs-lookup"><span data-stu-id="0adf5-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0adf5-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0adf5-122">Remarks</span></span>  
 <span data-ttu-id="0adf5-123">L'elemento `remove` rimuove il modulo di richiesta Web registrato per il prefisso URI specificato.</span><span class="sxs-lookup"><span data-stu-id="0adf5-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="0adf5-124">Il valore `prefix` dell'attributo deve essere costituito dai caratteri`http`iniziali di`http://www.contoso.com`un URI valido, ad esempio " " o " ".</span><span class="sxs-lookup"><span data-stu-id="0adf5-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="0adf5-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="0adf5-125">Configuration Files</span></span>  
 <span data-ttu-id="0adf5-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="0adf5-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0adf5-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="0adf5-127">Example</span></span>  

<span data-ttu-id="0adf5-128">Nell'esempio riportato di seguito viene rimosso il modulo di richiesta Web `www.contoso.com`esistente per HTTP, quindi viene registrato un nuovo modulo di richiesta Web personalizzato per le richieste HTTP in .</span><span class="sxs-lookup"><span data-stu-id="0adf5-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="0adf5-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0adf5-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="0adf5-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="0adf5-130">Network Settings Schema</span></span>](index.md)
