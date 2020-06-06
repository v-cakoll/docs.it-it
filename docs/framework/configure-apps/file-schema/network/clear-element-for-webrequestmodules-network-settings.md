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
ms.openlocfilehash: 5832d120824df75d374fc94cb0aa4e08189cb965
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088493"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="1f551-102">Elemento \<clear> per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="1f551-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="1f551-103">Rimuove tutti i moduli di richiesta Web registrati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1f551-103">Removes all registered Web request modules from the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="1f551-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f551-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f551-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1f551-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1f551-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1f551-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f551-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="1f551-107">Attributes</span></span>  
 <span data-ttu-id="1f551-108">No.</span><span class="sxs-lookup"><span data-stu-id="1f551-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1f551-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1f551-109">Child Elements</span></span>  
 <span data-ttu-id="1f551-110">No.</span><span class="sxs-lookup"><span data-stu-id="1f551-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f551-111">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1f551-111">Parent Elements</span></span>  
  
|<span data-ttu-id="1f551-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1f551-112">**Element**</span></span>|<span data-ttu-id="1f551-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1f551-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1f551-114">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="1f551-114">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="1f551-115">Specifica i moduli da usare per richiedere informazioni dagli host di rete.</span><span class="sxs-lookup"><span data-stu-id="1f551-115">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f551-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="1f551-116">Remarks</span></span>  
 <span data-ttu-id="1f551-117">L' `clear` elemento rimuove tutti i moduli di richiesta Web registrati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1f551-117">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1f551-118">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1f551-118">Configuration Files</span></span>  
 <span data-ttu-id="1f551-119">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1f551-119">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f551-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f551-120">Example</span></span>  
 <span data-ttu-id="1f551-121">Nell'esempio seguente vengono cancellati tutti i moduli di richiesta Web e quindi viene registrato un modulo di richiesta Web per HTTP.</span><span class="sxs-lookup"><span data-stu-id="1f551-121">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1f551-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1f551-122">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="1f551-123">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="1f551-123">Network Settings Schema</span></span>](index.md)
