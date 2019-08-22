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
ms.openlocfilehash: e175c70bd4932d6a8f9428e8cd9159a47df52558
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659432"
---
# <a name="clear-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="6d355-102">\<Cancella > elemento per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="6d355-102">\<clear> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="6d355-103">Rimuove tutti i moduli di richiesta Web registrati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6d355-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="6d355-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6d355-104">\<configuration></span></span>  
<span data-ttu-id="6d355-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6d355-105">\<system.net></span></span>  
<span data-ttu-id="6d355-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="6d355-106">\<webRequestModules></span></span>  
<span data-ttu-id="6d355-107">\<Cancella ></span><span class="sxs-lookup"><span data-stu-id="6d355-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d355-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6d355-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d355-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="6d355-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6d355-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="6d355-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d355-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="6d355-111">Attributes</span></span>  
 <span data-ttu-id="6d355-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6d355-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6d355-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6d355-113">Child Elements</span></span>  
 <span data-ttu-id="6d355-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="6d355-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d355-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="6d355-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6d355-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="6d355-116">**Element**</span></span>|<span data-ttu-id="6d355-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6d355-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="6d355-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="6d355-118">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="6d355-119">Specifica i moduli da usare per richiedere informazioni dagli host di rete.</span><span class="sxs-lookup"><span data-stu-id="6d355-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d355-120">Note</span><span class="sxs-lookup"><span data-stu-id="6d355-120">Remarks</span></span>  
 <span data-ttu-id="6d355-121">L' `clear` elemento rimuove tutti i moduli di richiesta Web registrati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6d355-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6d355-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="6d355-122">Configuration Files</span></span>  
 <span data-ttu-id="6d355-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="6d355-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d355-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d355-124">Example</span></span>  
 <span data-ttu-id="6d355-125">Nell'esempio seguente vengono cancellati tutti i moduli di richiesta Web e quindi viene registrato un modulo di richiesta Web per HTTP.</span><span class="sxs-lookup"><span data-stu-id="6d355-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6d355-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d355-126">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="6d355-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="6d355-127">Network Settings Schema</span></span>](index.md)
