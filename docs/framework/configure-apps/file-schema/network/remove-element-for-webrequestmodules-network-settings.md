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
ms.openlocfilehash: c57e2849d608b1706c41beca91ff8026ebd9ca45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705025"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="651d2-102">\<rimuovere > (elemento) per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="651d2-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="651d2-103">Rimuove un modulo di richiesta Web personalizzato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="651d2-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="651d2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="651d2-104">\<configuration></span></span>  
<span data-ttu-id="651d2-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="651d2-105">\<system.net></span></span>  
<span data-ttu-id="651d2-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="651d2-106">\<webRequestModules></span></span>  
<span data-ttu-id="651d2-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="651d2-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="651d2-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="651d2-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="651d2-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="651d2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="651d2-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="651d2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="651d2-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="651d2-111">Attributes</span></span>  
  
|<span data-ttu-id="651d2-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="651d2-112">**Attribute**</span></span>|<span data-ttu-id="651d2-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="651d2-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="651d2-114">Il prefisso URI per le richieste gestite da questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="651d2-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="651d2-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="651d2-115">Child Elements</span></span>  
 <span data-ttu-id="651d2-116">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="651d2-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="651d2-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="651d2-117">Parent Elements</span></span>  
  
|<span data-ttu-id="651d2-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="651d2-118">**Element**</span></span>|<span data-ttu-id="651d2-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="651d2-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="651d2-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="651d2-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="651d2-121">Specifica i moduli da utilizzare per richiedere informazioni da host di rete.</span><span class="sxs-lookup"><span data-stu-id="651d2-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="651d2-122">Note</span><span class="sxs-lookup"><span data-stu-id="651d2-122">Remarks</span></span>  
 <span data-ttu-id="651d2-123">Il `remove` elemento rimuove il modulo di richiesta Web registrato per il prefisso URI specificati.</span><span class="sxs-lookup"><span data-stu-id="651d2-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="651d2-124">Il valore per il `prefix` attributo deve essere i caratteri iniziali di un URI valido, ad esempio, "`http`", o "`http://www.contoso.com`".</span><span class="sxs-lookup"><span data-stu-id="651d2-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="651d2-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="651d2-125">Configuration Files</span></span>  
 <span data-ttu-id="651d2-126">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="651d2-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="651d2-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="651d2-127">Example</span></span>  

<span data-ttu-id="651d2-128">L'esempio seguente rimuove il modulo di richiesta Web esistente per HTTP e registra un nuovo modulo di richiesta Web personalizzato per il protocollo HTTP richiede `www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="651d2-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="651d2-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="651d2-129">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="651d2-130">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="651d2-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
