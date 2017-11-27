---
title: '&lt;deselezionare&gt; elemento per webRequestModules (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c88792663b07ace7250b6ee4065e60d6cfb90afd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="d267b-102">&lt;deselezionare&gt; elemento per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="d267b-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="d267b-103">Rimuove tutti i moduli di richiesta Web registrati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d267b-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="d267b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d267b-104">\<configuration></span></span>  
<span data-ttu-id="d267b-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="d267b-105">\<system.net></span></span>  
<span data-ttu-id="d267b-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="d267b-106">\<webRequestModules></span></span>  
<span data-ttu-id="d267b-107">\<Deselezionare ></span><span class="sxs-lookup"><span data-stu-id="d267b-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d267b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d267b-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d267b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d267b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d267b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d267b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d267b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d267b-111">Attributes</span></span>  
 <span data-ttu-id="d267b-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d267b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d267b-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d267b-113">Child Elements</span></span>  
 <span data-ttu-id="d267b-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d267b-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d267b-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d267b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d267b-116">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d267b-116">**Element**</span></span>|<span data-ttu-id="d267b-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d267b-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d267b-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="d267b-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="d267b-119">Specifica i moduli da utilizzare per richiedere informazioni agli host di rete.</span><span class="sxs-lookup"><span data-stu-id="d267b-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d267b-120">Note</span><span class="sxs-lookup"><span data-stu-id="d267b-120">Remarks</span></span>  
 <span data-ttu-id="d267b-121">Il `clear` elemento rimuove registrati tutti i moduli di richiesta Web sono stati definiti nel file di configurazione o a un livello superiore nella gerarchia di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d267b-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d267b-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d267b-122">Configuration Files</span></span>  
 <span data-ttu-id="d267b-123">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d267b-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d267b-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="d267b-124">Example</span></span>  
 <span data-ttu-id="d267b-125">Nell'esempio seguente cancella tutti i moduli di richiesta Web e viene registrato un modulo di richiesta Web per HTTP.</span><span class="sxs-lookup"><span data-stu-id="d267b-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d267b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d267b-126">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="d267b-127">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d267b-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
