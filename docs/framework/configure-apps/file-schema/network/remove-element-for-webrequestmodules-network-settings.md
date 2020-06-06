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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154725"
---
# <a name="remove-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="f29f1-102">Elemento \<remove> per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="f29f1-102">\<remove> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="f29f1-103">Rimuove un modulo di richiesta Web personalizzato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f29f1-103">Removes a custom Web request module from the application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**
  
## <a name="syntax"></a><span data-ttu-id="f29f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f29f1-104">Syntax</span></span>  
  
```xml  
<remove
  prefix="URI prefix"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f29f1-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f29f1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f29f1-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f29f1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f29f1-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f29f1-107">Attributes</span></span>  
  
|<span data-ttu-id="f29f1-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="f29f1-108">**Attribute**</span></span>|<span data-ttu-id="f29f1-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f29f1-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="f29f1-110">Prefisso URI per le richieste gestite da questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="f29f1-110">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f29f1-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f29f1-111">Child Elements</span></span>  
 <span data-ttu-id="f29f1-112">No.</span><span class="sxs-lookup"><span data-stu-id="f29f1-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f29f1-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f29f1-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f29f1-114">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="f29f1-114">**Element**</span></span>|<span data-ttu-id="f29f1-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f29f1-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f29f1-116">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="f29f1-116">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="f29f1-117">Specifica i moduli da usare per richiedere informazioni dagli host di rete.</span><span class="sxs-lookup"><span data-stu-id="f29f1-117">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f29f1-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="f29f1-118">Remarks</span></span>  
 <span data-ttu-id="f29f1-119">L' `remove` elemento rimuove il modulo di richiesta Web registrato per il prefisso URI specificato.</span><span class="sxs-lookup"><span data-stu-id="f29f1-119">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="f29f1-120">Il valore dell' `prefix` attributo deve essere costituito dai caratteri iniziali di un URI valido, ad esempio " `http` " o " `http://www.contoso.com` ".</span><span class="sxs-lookup"><span data-stu-id="f29f1-120">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "`http`", or "`http://www.contoso.com`".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f29f1-121">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="f29f1-121">Configuration Files</span></span>  
 <span data-ttu-id="f29f1-122">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f29f1-122">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f29f1-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="f29f1-123">Example</span></span>  

<span data-ttu-id="f29f1-124">Nell'esempio seguente viene rimosso il modulo di richiesta Web esistente per HTTP, quindi viene registrato un nuovo modulo di richiesta Web personalizzato per le richieste HTTP a `www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f29f1-124">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to `www.contoso.com`.</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="f29f1-125">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f29f1-125">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="f29f1-126">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="f29f1-126">Network Settings Schema</span></span>](index.md)
