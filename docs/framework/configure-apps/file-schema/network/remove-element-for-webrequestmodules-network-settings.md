---
title: '&lt;rimuovere&gt; (elemento) per webRequestModules (impostazioni di rete)'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d0da0fd2edae4687ea80b4a23cc82a25ead9cb7b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47208581"
---
# <a name="ltremovegt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="c5b66-102">&lt;rimuovere&gt; (elemento) per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="c5b66-102">&lt;remove&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="c5b66-103">Rimuove un modulo di richiesta Web personalizzato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c5b66-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="c5b66-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c5b66-104">\<configuration></span></span>  
<span data-ttu-id="c5b66-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="c5b66-105">\<system.net></span></span>  
<span data-ttu-id="c5b66-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="c5b66-106">\<webRequestModules></span></span>  
<span data-ttu-id="c5b66-107">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="c5b66-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b66-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5b66-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5b66-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c5b66-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c5b66-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c5b66-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5b66-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c5b66-111">Attributes</span></span>  
  
|<span data-ttu-id="c5b66-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="c5b66-112">**Attribute**</span></span>|<span data-ttu-id="c5b66-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c5b66-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="c5b66-114">Il prefisso URI per le richieste gestite da questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="c5b66-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5b66-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c5b66-115">Child Elements</span></span>  
 <span data-ttu-id="c5b66-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c5b66-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5b66-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c5b66-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c5b66-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="c5b66-118">**Element**</span></span>|<span data-ttu-id="c5b66-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c5b66-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c5b66-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="c5b66-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="c5b66-121">Specifica i moduli da utilizzare per richiedere informazioni da host di rete.</span><span class="sxs-lookup"><span data-stu-id="c5b66-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5b66-122">Note</span><span class="sxs-lookup"><span data-stu-id="c5b66-122">Remarks</span></span>  
 <span data-ttu-id="c5b66-123">Il `remove` elemento rimuove il modulo di richiesta Web registrato per il prefisso URI specificati.</span><span class="sxs-lookup"><span data-stu-id="c5b66-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="c5b66-124">Il valore per il `prefix` attributo deve corrispondere ai caratteri iniziali di un URI valido, ad esempio, "http", o "`http://www.contoso.com` ".</span><span class="sxs-lookup"><span data-stu-id="c5b66-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "http", or "`http://www.contoso.com` ".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c5b66-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c5b66-125">Configuration Files</span></span>  
 <span data-ttu-id="c5b66-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c5b66-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5b66-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5b66-127">Example</span></span>  
 <span data-ttu-id="c5b66-128">Nell'esempio seguente rimuove il modulo di richiesta Web esistente per HTTP e viene registrato un nuovo modulo di richiesta Web personalizzato per le richieste HTTP per www.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c5b66-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to www.contoso.com.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c5b66-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5b66-129">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="c5b66-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="c5b66-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
