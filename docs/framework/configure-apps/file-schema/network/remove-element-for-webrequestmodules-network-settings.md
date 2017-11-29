---
title: '&lt;rimuovere&gt; elemento per webRequestModules (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 43f0d30f8c18c4755f31d0c851c773207bc15b78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="5df53-102">&lt;rimuovere&gt; elemento per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="5df53-102">&lt;remove&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="5df53-103">Rimuove un modulo di richiesta Web personalizzato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5df53-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="5df53-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5df53-104">\<configuration></span></span>  
<span data-ttu-id="5df53-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="5df53-105">\<system.net></span></span>  
<span data-ttu-id="5df53-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="5df53-106">\<webRequestModules></span></span>  
<span data-ttu-id="5df53-107">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="5df53-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5df53-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5df53-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5df53-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="5df53-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5df53-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="5df53-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5df53-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="5df53-111">Attributes</span></span>  
  
|<span data-ttu-id="5df53-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="5df53-112">**Attribute**</span></span>|<span data-ttu-id="5df53-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5df53-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="5df53-114">Il prefisso URI per le richieste gestite da questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="5df53-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5df53-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="5df53-115">Child Elements</span></span>  
 <span data-ttu-id="5df53-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="5df53-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5df53-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="5df53-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5df53-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="5df53-118">**Element**</span></span>|<span data-ttu-id="5df53-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5df53-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5df53-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="5df53-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="5df53-121">Specifica i moduli da utilizzare per richiedere informazioni agli host di rete.</span><span class="sxs-lookup"><span data-stu-id="5df53-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5df53-122">Note</span><span class="sxs-lookup"><span data-stu-id="5df53-122">Remarks</span></span>  
 <span data-ttu-id="5df53-123">Il `remove` elemento rimuove il modulo di richiesta Web registrato per il prefisso URI specificato.</span><span class="sxs-lookup"><span data-stu-id="5df53-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="5df53-124">Il valore per il `prefix` attributo deve corrispondere ai caratteri iniziali di un URI valido, ad esempio, "http" o "http://www.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="5df53-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "http", or "http://www.contoso.com".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5df53-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="5df53-125">Configuration Files</span></span>  
 <span data-ttu-id="5df53-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5df53-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5df53-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="5df53-127">Example</span></span>  
 <span data-ttu-id="5df53-128">Nell'esempio seguente rimuove il modulo di richiesta Web esistente per HTTP e viene registrato un nuovo modulo di richiesta Web personalizzato per le richieste HTTP a www.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5df53-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to www.contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5df53-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5df53-129">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="5df53-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="5df53-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
