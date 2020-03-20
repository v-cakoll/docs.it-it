---
title: Elemento <add> per webRequestModules (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
ms.openlocfilehash: f4edce948033478aab59a2aff61abadc55a327ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155024"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="82e79-102">\<Add> elemento per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="82e79-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="82e79-103">Aggiunge un modulo di richiesta Web personalizzato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="82e79-103">Adds a custom Web request module to the application.</span></span>  

<span data-ttu-id="82e79-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="82e79-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="82e79-105">&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="82e79-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="82e79-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>webRequestModules**](webrequestmodules-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="82e79-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)</span></span>\
<span data-ttu-id="82e79-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<aggiungere>**</span><span class="sxs-lookup"><span data-stu-id="82e79-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="82e79-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82e79-108">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82e79-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="82e79-109">Attributes and Elements</span></span>  
 <span data-ttu-id="82e79-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="82e79-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82e79-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="82e79-111">Attributes</span></span>  
  
|<span data-ttu-id="82e79-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="82e79-112">**Attribute**</span></span>|<span data-ttu-id="82e79-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="82e79-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="82e79-114">Prefisso URI per le richieste gestite da questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="82e79-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="82e79-115">Il nome completo del <xref:System.Type.FullName%2A> tipo (indicato dalla proprietà) e il <xref:System.Reflection.Assembly.FullName%2A> nome dell'assembly (indicato dalla proprietà), separati da una virgola, che implementa questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="82e79-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82e79-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="82e79-116">Child Elements</span></span>  
 <span data-ttu-id="82e79-117">No.</span><span class="sxs-lookup"><span data-stu-id="82e79-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82e79-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="82e79-118">Parent Elements</span></span>  
  
|<span data-ttu-id="82e79-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="82e79-119">**Element**</span></span>|<span data-ttu-id="82e79-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="82e79-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="82e79-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="82e79-121">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="82e79-122">Specifica i moduli da utilizzare per richiedere informazioni agli host di rete.</span><span class="sxs-lookup"><span data-stu-id="82e79-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82e79-123">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="82e79-123">Remarks</span></span>  
 <span data-ttu-id="82e79-124">L'attributo `prefix` definisce il prefisso URI che utilizza il modulo di richiesta Web specificato.</span><span class="sxs-lookup"><span data-stu-id="82e79-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="82e79-125">I moduli di richiesta Web vengono in genere registrati per gestire un protocollo specifico, ad esempio HTTP o FTP, ma possono essere registrati per gestire una richiesta a un server o un percorso specifico in un server.</span><span class="sxs-lookup"><span data-stu-id="82e79-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="82e79-126">Il modulo di richiesta Web viene creato quando <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> un URI corrispondente al prefisso viene passato al metodo.</span><span class="sxs-lookup"><span data-stu-id="82e79-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="82e79-127">Il valore `prefix` per l'attributo deve essere costituito dai caratteri iniziali di un URI valido.</span><span class="sxs-lookup"><span data-stu-id="82e79-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="82e79-128">Ad esempio, `http` o `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="82e79-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="82e79-129">Il valore `type` dell'attributo deve essere un nome di tipo valido e il nome dell'assembly corrispondente, separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="82e79-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="82e79-130">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="82e79-130">Configuration Files</span></span>  
 <span data-ttu-id="82e79-131">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="82e79-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82e79-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="82e79-132">Example</span></span>  
 <span data-ttu-id="82e79-133">Nell'esempio seguente viene registrato un modulo di richiesta Web personalizzato per HTTP.</span><span class="sxs-lookup"><span data-stu-id="82e79-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="82e79-134">È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="82e79-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="82e79-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82e79-135">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="82e79-136">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="82e79-136">Network Settings Schema</span></span>](index.md)
