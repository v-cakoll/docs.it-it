---
title: '&lt;aggiungere&gt; (elemento) per webRequestModules (impostazioni di rete)'
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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 64df186be7d9e503ac22e177bca8da31e165f240
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266311"
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="58d8b-102">&lt;aggiungere&gt; (elemento) per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="58d8b-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="58d8b-103">Aggiunge un modulo di richiesta Web personalizzato per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="58d8b-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="58d8b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="58d8b-104">\<configuration></span></span>  
<span data-ttu-id="58d8b-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="58d8b-105">\<system.net></span></span>  
<span data-ttu-id="58d8b-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="58d8b-106">\<webRequestModules></span></span>  
<span data-ttu-id="58d8b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="58d8b-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d8b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58d8b-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58d8b-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="58d8b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="58d8b-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="58d8b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58d8b-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="58d8b-111">Attributes</span></span>  
  
|<span data-ttu-id="58d8b-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="58d8b-112">**Attribute**</span></span>|<span data-ttu-id="58d8b-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="58d8b-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="58d8b-114">Il prefisso URI per le richieste gestite da questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="58d8b-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="58d8b-115">Il nome completo del tipo (indicato dal <xref:System.Type.FullName%2A> proprietà) e il nome dell'assembly (indicato dal <xref:System.Reflection.Assembly.FullName%2A> proprietà), separati da una virgola, che implementa questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="58d8b-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58d8b-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="58d8b-116">Child Elements</span></span>  
 <span data-ttu-id="58d8b-117">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="58d8b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58d8b-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="58d8b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="58d8b-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="58d8b-119">**Element**</span></span>|<span data-ttu-id="58d8b-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="58d8b-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="58d8b-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="58d8b-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="58d8b-122">Specifica i moduli da utilizzare per richiedere informazioni da host di rete.</span><span class="sxs-lookup"><span data-stu-id="58d8b-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58d8b-123">Note</span><span class="sxs-lookup"><span data-stu-id="58d8b-123">Remarks</span></span>  
 <span data-ttu-id="58d8b-124">Il `prefix` attributo definisce il prefisso URI che usa il modulo di richiesta Web specificato.</span><span class="sxs-lookup"><span data-stu-id="58d8b-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="58d8b-125">Moduli di richiesta Web sono in genere registrati per gestire un protocollo specifico, ad esempio HTTP o FTP, ma possono essere registrati per gestire una richiesta a un server specifico o un percorso in un server.</span><span class="sxs-lookup"><span data-stu-id="58d8b-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="58d8b-126">Il modulo di richiesta Web viene creato quando viene passato un prefisso corrispondente a un URI per il <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> (metodo).</span><span class="sxs-lookup"><span data-stu-id="58d8b-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="58d8b-127">Il valore per il `prefix` attributo deve corrispondere ai caratteri iniziali di un URI valido.</span><span class="sxs-lookup"><span data-stu-id="58d8b-127">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="58d8b-128">Ad esempio, `http` o `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="58d8b-128">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="58d8b-129">Il valore per il `type` attributo deve essere un nome di tipo valido e il corrispondente nome dell'assembly, separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="58d8b-129">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="58d8b-130">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="58d8b-130">Configuration Files</span></span>  
 <span data-ttu-id="58d8b-131">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="58d8b-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58d8b-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="58d8b-132">Example</span></span>  
 <span data-ttu-id="58d8b-133">Nell'esempio seguente registra un modulo di richiesta Web personalizzato per il protocollo HTTP.</span><span class="sxs-lookup"><span data-stu-id="58d8b-133">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="58d8b-134">È necessario sostituire i valori per la versione e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="58d8b-134">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="58d8b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58d8b-135">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="58d8b-136">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="58d8b-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
