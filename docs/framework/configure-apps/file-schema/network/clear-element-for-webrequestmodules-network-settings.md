---
title: Elemento <clear> per webRequestModules (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
ms.openlocfilehash: 95a190dac3a9512b404a054c60c48de9c4574790
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698331"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="ea781-102">Elemento > \<clear per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="ea781-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="ea781-103">Rimuove tutti i moduli di richiesta Web registrati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ea781-103">Removes all registered Web request modules from the application.</span></span>  
  
[<span data-ttu-id="ea781-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ea781-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ea781-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ea781-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="ea781-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<webRequestModules >** ](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="ea781-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>  
<span data-ttu-id="ea781-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="ea781-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea781-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea781-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea781-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ea781-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ea781-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ea781-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea781-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="ea781-111">Attributes</span></span>  
 <span data-ttu-id="ea781-112">No.</span><span class="sxs-lookup"><span data-stu-id="ea781-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ea781-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ea781-113">Child Elements</span></span>  
 <span data-ttu-id="ea781-114">No.</span><span class="sxs-lookup"><span data-stu-id="ea781-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea781-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ea781-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ea781-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ea781-116">**Element**</span></span>|<span data-ttu-id="ea781-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ea781-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ea781-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="ea781-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="ea781-119">Specifica i moduli da usare per richiedere informazioni dagli host di rete.</span><span class="sxs-lookup"><span data-stu-id="ea781-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea781-120">Note</span><span class="sxs-lookup"><span data-stu-id="ea781-120">Remarks</span></span>  
 <span data-ttu-id="ea781-121">L'elemento `clear` rimuove tutti i moduli di richiesta Web registrati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ea781-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="ea781-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ea781-122">Configuration Files</span></span>  
 <span data-ttu-id="ea781-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ea781-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea781-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="ea781-124">Example</span></span>  
 <span data-ttu-id="ea781-125">Nell'esempio seguente vengono cancellati tutti i moduli di richiesta Web e quindi viene registrato un modulo di richiesta Web per HTTP.</span><span class="sxs-lookup"><span data-stu-id="ea781-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea781-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea781-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="ea781-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="ea781-127">Network Settings Schema</span></span>](index.md)
