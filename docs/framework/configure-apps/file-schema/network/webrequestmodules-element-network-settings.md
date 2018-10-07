---
title: '&lt;webRequestModules&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7cd25b980afa067ac78fc081c0a7a8e65a23258b
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838260"
---
# <a name="ltwebrequestmodulesgt-element-network-settings"></a><span data-ttu-id="e68fb-102">&lt;webRequestModules&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="e68fb-102">&lt;webRequestModules&gt; Element (Network Settings)</span></span>
<span data-ttu-id="e68fb-103">Specifica i moduli da utilizzare per richiedere informazioni da host di rete.</span><span class="sxs-lookup"><span data-stu-id="e68fb-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="e68fb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e68fb-104">\<configuration></span></span>  
<span data-ttu-id="e68fb-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e68fb-105">\<system.net></span></span>  
<span data-ttu-id="e68fb-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="e68fb-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e68fb-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e68fb-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e68fb-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e68fb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e68fb-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e68fb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e68fb-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="e68fb-110">Attributes</span></span>  
 <span data-ttu-id="e68fb-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e68fb-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e68fb-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e68fb-112">Child Elements</span></span>  
  
|<span data-ttu-id="e68fb-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e68fb-113">**Element**</span></span>|<span data-ttu-id="e68fb-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e68fb-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e68fb-115">add</span><span class="sxs-lookup"><span data-stu-id="e68fb-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="e68fb-116">Aggiunge un modulo di richiesta Web personalizzato per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e68fb-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="e68fb-117">clear</span><span class="sxs-lookup"><span data-stu-id="e68fb-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="e68fb-118">Rimuove tutti i moduli di richiesta Web registrati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e68fb-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="e68fb-119">remove</span><span class="sxs-lookup"><span data-stu-id="e68fb-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="e68fb-120">Rimuove un modulo di richiesta Web personalizzato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e68fb-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e68fb-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e68fb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e68fb-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e68fb-122">**Element**</span></span>|<span data-ttu-id="e68fb-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e68fb-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e68fb-124">System.NET</span><span class="sxs-lookup"><span data-stu-id="e68fb-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="e68fb-125">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e68fb-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e68fb-126">Note</span><span class="sxs-lookup"><span data-stu-id="e68fb-126">Remarks</span></span>  
 <span data-ttu-id="e68fb-127">Con l'elemento `webRequestModules` vengono registrati i discendenti della classe <xref:System.Net.WebRequest> per gestire le richieste di informazioni inviate agli host di rete.</span><span class="sxs-lookup"><span data-stu-id="e68fb-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="e68fb-128">Moduli di richiesta Web devono implementare il <xref:System.Net.IWebRequestCreate> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e68fb-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="e68fb-129">.NET Framework include i moduli di richiesta Web per gli URI che iniziano con `http://`, `https://`, e `file://`.</span><span class="sxs-lookup"><span data-stu-id="e68fb-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="e68fb-130">È possibile sostituire i moduli predefiniti solo tramite la registrazione di un modulo personalizzato nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e68fb-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e68fb-131">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e68fb-131">Configuration Files</span></span>  
 <span data-ttu-id="e68fb-132">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e68fb-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e68fb-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="e68fb-133">Example</span></span>  
 <span data-ttu-id="e68fb-134">Nell'esempio seguente registra il modulo HTTP predefinito.</span><span class="sxs-lookup"><span data-stu-id="e68fb-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="e68fb-135">È necessario sostituire i valori per la versione e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="e68fb-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e68fb-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e68fb-136">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.IWebRequestCreate>  
 [<span data-ttu-id="e68fb-137">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e68fb-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
