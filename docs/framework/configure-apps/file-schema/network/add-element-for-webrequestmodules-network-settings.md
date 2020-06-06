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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155024"
---
# <a name="add-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="7e97a-102">Elemento \<add> per webRequestModules (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="7e97a-102">\<add> Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="7e97a-103">Aggiunge un modulo di richiesta Web personalizzato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7e97a-103">Adds a custom Web request module to the application.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<webRequestModules>**](webrequestmodules-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="7e97a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e97a-104">Syntax</span></span>  
  
```xml  
<add
  prefix="URI prefix"
  type="type_fullname, assembly_fullname"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e97a-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7e97a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7e97a-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7e97a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e97a-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="7e97a-107">Attributes</span></span>  
  
|<span data-ttu-id="7e97a-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="7e97a-108">**Attribute**</span></span>|<span data-ttu-id="7e97a-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7e97a-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="7e97a-110">Prefisso URI per le richieste gestite da questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="7e97a-110">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="7e97a-111">Il nome completo del tipo (indicato dalla <xref:System.Type.FullName%2A> proprietà) e il nome dell'assembly (indicato dalla <xref:System.Reflection.Assembly.FullName%2A> proprietà), separati da una virgola, che implementa questo modulo di richiesta Web.</span><span class="sxs-lookup"><span data-stu-id="7e97a-111">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e97a-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7e97a-112">Child Elements</span></span>  
 <span data-ttu-id="7e97a-113">No.</span><span class="sxs-lookup"><span data-stu-id="7e97a-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e97a-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7e97a-114">Parent Elements</span></span>  
  
|<span data-ttu-id="7e97a-115">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="7e97a-115">**Element**</span></span>|<span data-ttu-id="7e97a-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="7e97a-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="7e97a-117">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="7e97a-117">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="7e97a-118">Specifica i moduli da usare per richiedere informazioni dagli host di rete.</span><span class="sxs-lookup"><span data-stu-id="7e97a-118">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e97a-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="7e97a-119">Remarks</span></span>  
 <span data-ttu-id="7e97a-120">L' `prefix` attributo definisce il prefisso URI che usa il modulo di richiesta Web specificato.</span><span class="sxs-lookup"><span data-stu-id="7e97a-120">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="7e97a-121">I moduli di richiesta Web vengono in genere registrati per gestire un protocollo specifico, ad esempio HTTP o FTP, ma possono essere registrati per gestire una richiesta a un server o a un percorso specifico in un server.</span><span class="sxs-lookup"><span data-stu-id="7e97a-121">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="7e97a-122">Il modulo della richiesta Web viene creato quando un prefisso corrispondente URI viene passato al <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="7e97a-122">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="7e97a-123">Il valore dell' `prefix` attributo deve essere costituito dai caratteri iniziali di un URI valido.</span><span class="sxs-lookup"><span data-stu-id="7e97a-123">The value for the `prefix` attribute should be the leading characters of a valid URI.</span></span> <span data-ttu-id="7e97a-124">Ad esempio, `http` o `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="7e97a-124">For example, `http` or `http://www.contoso.com`.</span></span>
  
 <span data-ttu-id="7e97a-125">Il valore dell' `type` attributo deve essere un nome di tipo valido e un nome di assembly corrispondente, separati da una virgola.</span><span class="sxs-lookup"><span data-stu-id="7e97a-125">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma.</span></span>
  
## <a name="configuration-files"></a><span data-ttu-id="7e97a-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="7e97a-126">Configuration Files</span></span>  
 <span data-ttu-id="7e97a-127">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7e97a-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e97a-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e97a-128">Example</span></span>  
 <span data-ttu-id="7e97a-129">Nell'esempio seguente viene registrato un modulo di richiesta Web personalizzato per HTTP.</span><span class="sxs-lookup"><span data-stu-id="7e97a-129">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="7e97a-130">È necessario sostituire i valori per Version e PublicKeyToken con i valori corretti per il modulo specificato.</span><span class="sxs-lookup"><span data-stu-id="7e97a-130">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7e97a-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="7e97a-131">See also</span></span>

- <xref:System.Net.WebRequest>
- [<span data-ttu-id="7e97a-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="7e97a-132">Network Settings Schema</span></span>](index.md)
