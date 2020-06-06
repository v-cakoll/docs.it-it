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
ms.openlocfilehash: 7f2805283f89e6165d336b3e593d34054e02115d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154543"
---
# <a name="webrequestmodules-element-network-settings"></a><span data-ttu-id="1b523-102">Elemento \<webRequestModules> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="1b523-102">\<webRequestModules> Element (Network Settings)</span></span>
<span data-ttu-id="1b523-103">Specifica i moduli da usare per richiedere informazioni dagli host di rete.</span><span class="sxs-lookup"><span data-stu-id="1b523-103">Specifies modules to use to request information from network hosts.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;\<webRequestModules>  
  
## <a name="syntax"></a><span data-ttu-id="1b523-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b523-104">Syntax</span></span>  
  
```xml  
<webRequestModules>
</webRequestModules>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b523-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1b523-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1b523-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1b523-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b523-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="1b523-107">Attributes</span></span>  
 <span data-ttu-id="1b523-108">No.</span><span class="sxs-lookup"><span data-stu-id="1b523-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1b523-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1b523-109">Child Elements</span></span>  
  
|<span data-ttu-id="1b523-110">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1b523-110">**Element**</span></span>|<span data-ttu-id="1b523-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1b523-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1b523-112">add</span><span class="sxs-lookup"><span data-stu-id="1b523-112">add</span></span>](add-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="1b523-113">Aggiunge un modulo di richiesta Web personalizzato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1b523-113">Adds a custom Web request module to the application.</span></span>|  
|[<span data-ttu-id="1b523-114">deselezionare</span><span class="sxs-lookup"><span data-stu-id="1b523-114">clear</span></span>](clear-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="1b523-115">Rimuove tutti i moduli di richiesta Web registrati dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1b523-115">Removes all registered Web request modules from the application.</span></span>|  
|[<span data-ttu-id="1b523-116">remove</span><span class="sxs-lookup"><span data-stu-id="1b523-116">remove</span></span>](remove-element-for-webrequestmodules-network-settings.md)|<span data-ttu-id="1b523-117">Rimuove un modulo di richiesta Web personalizzato dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1b523-117">Removes a custom Web request module from the application.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1b523-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1b523-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1b523-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="1b523-119">**Element**</span></span>|<span data-ttu-id="1b523-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="1b523-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1b523-121">system.net</span><span class="sxs-lookup"><span data-stu-id="1b523-121">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="1b523-122">Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1b523-122">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b523-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="1b523-123">Remarks</span></span>  
 <span data-ttu-id="1b523-124">Con l'elemento `webRequestModules` vengono registrati i discendenti della classe <xref:System.Net.WebRequest> per gestire le richieste di informazioni inviate agli host di rete.</span><span class="sxs-lookup"><span data-stu-id="1b523-124">The `webRequestModules` element registers descendants of the <xref:System.Net.WebRequest> class to handle information requests to network hosts.</span></span> <span data-ttu-id="1b523-125">I moduli di richiesta Web devono implementare l' <xref:System.Net.IWebRequestCreate> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1b523-125">Web request modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span>  
  
 <span data-ttu-id="1b523-126">Il .NET Framework include i moduli di richiesta Web per gli URI che iniziano con `http://` , `https://` e `file://` .</span><span class="sxs-lookup"><span data-stu-id="1b523-126">The .NET Framework includes Web request modules for URIs that begin with `http://`, `https://`, and `file://`.</span></span> <span data-ttu-id="1b523-127">È possibile eseguire l'override dei moduli predefiniti solo registrando un modulo personalizzato nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1b523-127">You can override the default modules only by registering a custom module in the configuration file.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1b523-128">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1b523-128">Configuration Files</span></span>  
 <span data-ttu-id="1b523-129">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1b523-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b523-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="1b523-130">Example</span></span>  
 <span data-ttu-id="1b523-131">Nell'esempio seguente viene registrato il modulo HTTP predefinito.</span><span class="sxs-lookup"><span data-stu-id="1b523-131">The following example registers the default HTTP module.</span></span> <span data-ttu-id="1b523-132">È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="1b523-132">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b523-133">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1b523-133">See also</span></span>

- <xref:System.Net.WebRequest>
- <xref:System.Net.IWebRequestCreate>
- [<span data-ttu-id="1b523-134">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="1b523-134">Network Settings Schema</span></span>](index.md)
