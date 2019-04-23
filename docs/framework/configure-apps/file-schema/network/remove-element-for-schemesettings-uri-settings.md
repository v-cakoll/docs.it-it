---
title: Elemento <remove> per schemeSettings (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: f29ee86deaa150324b40f4fac12ead152553e50d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104975"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="4c551-102">\<rimuovere > (elemento) per schemeSettings (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="4c551-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="4c551-103">Rimuove un'impostazione di schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="4c551-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="4c551-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4c551-104">\<configuration></span></span>  
<span data-ttu-id="4c551-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="4c551-105">\<uri></span></span>  
<span data-ttu-id="4c551-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="4c551-106">\<schemeSettings></span></span>  
<span data-ttu-id="4c551-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="4c551-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c551-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c551-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c551-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4c551-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4c551-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4c551-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c551-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4c551-111">Attributes</span></span>  
  
|<span data-ttu-id="4c551-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="4c551-112">Attribute</span></span>|<span data-ttu-id="4c551-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c551-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c551-114">name</span><span class="sxs-lookup"><span data-stu-id="4c551-114">name</span></span>|<span data-ttu-id="4c551-115">Il nome dello schema per il quale si applica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="4c551-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="4c551-116">Il solo valori supportati sono: nome = "http" e nome = "https".</span><span class="sxs-lookup"><span data-stu-id="4c551-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c551-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4c551-117">Child Elements</span></span>  
 <span data-ttu-id="4c551-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4c551-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c551-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4c551-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4c551-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c551-120">Element</span></span>|<span data-ttu-id="4c551-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c551-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c551-122">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="4c551-122">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="4c551-123">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="4c551-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c551-124">Note</span><span class="sxs-lookup"><span data-stu-id="4c551-124">Remarks</span></span>  
 <span data-ttu-id="4c551-125">Per impostazione predefinita, il <xref:System.Uri?displayProperty=nameWithType> delimitatori di percorso con codifica percentuale non consente l'escape di classe prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="4c551-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="4c551-126">È stato implementato come un meccanismo di protezione contro gli attacchi simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4c551-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="4c551-127">Se viene passato questo URI lungo i moduli non gestiscono percento codificati in caratteri correttamente, potrebbero verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="4c551-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="4c551-128">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> prima i delimitatori di percorso non consente l'escape di classi e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="4c551-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="4c551-129">Il risultato di passare l'URL dannoso a <xref:System.Uri?displayProperty=nameWithType> costruttore di classe nell'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="4c551-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="4c551-130">Possibile è possibile modificare questo comportamento predefinito per non i delimitatori del percorso con codifica percentuale ONU-escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="4c551-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4c551-131">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="4c551-131">Configuration Files</span></span>  
 <span data-ttu-id="4c551-132">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4c551-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c551-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c551-133">Example</span></span>  
 <span data-ttu-id="4c551-134">Nell'esempio seguente mostra una configurazione usata dal <xref:System.Uri> classe che rimuove qualsiasi impostazione dello schema per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="4c551-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c551-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c551-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="4c551-136">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="4c551-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
