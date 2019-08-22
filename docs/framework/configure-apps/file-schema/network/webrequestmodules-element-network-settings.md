---
title: Elemento <webRequestModules> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webRequestModules
helpviewer_keywords:
- webRequestModules element
- <webRequestModules> element
ms.assetid: 1263de11-3e0a-4f94-97c9-710b2ae53817
ms.openlocfilehash: c30a7a0bcce62c99d7c1ec0ff17389b8c2cd2f17
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663936"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="38480-102">\<Elemento > webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="38480-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="38480-103">Specifica i moduli da usare per richiedere informazioni dagli host di rete.</span><span class="sxs-lookup"><span data-stu-id="38480-103">Specifies modules to use to request information from network hosts.</span></span>  
  
 <span data-ttu-id="38480-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="38480-104">\<configuration></span></span>  
<span data-ttu-id="38480-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="38480-105">\<system.net></span></span>  
<span data-ttu-id="38480-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="38480-106">\<webRequestModules></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38480-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38480-107">Syntax</span></span>  
  
```xml  
<webRequestModules>   
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38480-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="38480-108">Attributes and Elements</span></span>  
 <span data-ttu-id="38480-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="38480-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38480-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="38480-110">Attributes</span></span>  
 <span data-ttu-id="38480-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="38480-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="38480-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="38480-112">Child Elements</span></span>  
  
|<span data-ttu-id="38480-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="38480-113">**Element**</span></span>|<span data-ttu-id="38480-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="38480-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="38480-115">add</span><span class="sxs-lookup"><span data-stu-id="38480-115">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="38480-116">Aggiunge un modulo di richiesta Web personalizzato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38480-116">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="38480-117">clear</span><span class="sxs-lookup"><span data-stu-id="38480-117">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="38480-118">Rimuove tutti i moduli di richiesta Web registrati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38480-118">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="38480-119">remove</span><span class="sxs-lookup"><span data-stu-id="38480-119">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="38480-120">Rimuove un modulo di richiesta Web personalizzato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38480-120">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38480-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="38480-121">Parent Elements</span></span>  
  
|<span data-ttu-id="38480-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="38480-122">**Element**</span></span>|<span data-ttu-id="38480-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="38480-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="38480-124">system.net</span><span class="sxs-lookup"><span data-stu-id="38480-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="38480-125">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38480-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38480-126">Note</span><span class="sxs-lookup"><span data-stu-id="38480-126">Remarks</span></span>  
 <span data-ttu-id="38480-127">Con l'elemento `webRequestModules` vengono registrati i discendenti della classe <xref:System.Net.WebRequest> per gestire le richieste di informazioni inviate agli host di rete.</span><span class="sxs-lookup"><span data-stu-id="38480-127">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="38480-128">I moduli di richiesta Web devono <xref:System.Net.IWebRequestCreate> implementare l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="38480-128">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="38480-129">Il .NET Framework include i moduli di richiesta Web per gli URI `http://`che `https://`iniziano con `file://`, e.</span><span class="sxs-lookup"><span data-stu-id="38480-129">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="38480-130">È possibile eseguire l'override dei moduli predefiniti solo registrando un modulo personalizzato nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="38480-130">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="38480-131">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="38480-131">Configuration Files</span></span>  
 <span data-ttu-id="38480-132">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="38480-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38480-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="38480-133">Example</span></span>  
 <span data-ttu-id="38480-134">Nell'esempio seguente viene registrato il modulo HTTP predefinito.</span><span class="sxs-lookup"><span data-stu-id="38480-134">The following example registers the default HTTP module.</span></span> <span data-ttu-id="38480-135">È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="38480-135">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="38480-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38480-136">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="38480-137">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="38480-137">Network Settings Schema</span></span>](index.md)
