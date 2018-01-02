---
title: '&lt;rimuovere&gt; elemento per schemeSettings (impostazioni Uri)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
caps.latest.revision: "5"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7ab053937587d9cfd9353fe53fa759e58859e3da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="1bf60-102">&lt;rimuovere&gt; elemento per schemeSettings (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="1bf60-102">&lt;remove&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="1bf60-103">Rimuove un'impostazione dello schema per il nome di schema.</span><span class="sxs-lookup"><span data-stu-id="1bf60-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="1bf60-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1bf60-104">\<configuration></span></span>  
<span data-ttu-id="1bf60-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="1bf60-105">\<uri></span></span>  
<span data-ttu-id="1bf60-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="1bf60-106">\<schemeSettings></span></span>  
<span data-ttu-id="1bf60-107">\<rimuovere ></span><span class="sxs-lookup"><span data-stu-id="1bf60-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bf60-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bf60-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bf60-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1bf60-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1bf60-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1bf60-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bf60-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="1bf60-111">Attributes</span></span>  
  
|<span data-ttu-id="1bf60-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="1bf60-112">Attribute</span></span>|<span data-ttu-id="1bf60-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bf60-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bf60-114">name</span><span class="sxs-lookup"><span data-stu-id="1bf60-114">name</span></span>|<span data-ttu-id="1bf60-115">Il nome dello schema a cui si applica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="1bf60-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="1bf60-116">Il solo valori supportati sono name = "http" e nome = "https".</span><span class="sxs-lookup"><span data-stu-id="1bf60-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bf60-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1bf60-117">Child Elements</span></span>  
 <span data-ttu-id="1bf60-118">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="1bf60-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bf60-119">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1bf60-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1bf60-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1bf60-120">Element</span></span>|<span data-ttu-id="1bf60-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bf60-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bf60-122">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="1bf60-122">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="1bf60-123">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="1bf60-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bf60-124">Note</span><span class="sxs-lookup"><span data-stu-id="1bf60-124">Remarks</span></span>  
 <span data-ttu-id="1bf60-125">Per impostazione predefinita, il <xref:System.Uri?displayProperty=nameWithType> delimitatori di percorso con codifica percentuale non consente l'escape di classe prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="1bf60-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="1bf60-126">È stato implementato come un meccanismo di protezione contro gli attacchi simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1bf60-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="1bf60-127">Se questo URI viene passato a moduli non gestiscono percentuale correttamente codificati in caratteri, potrebbe verificarsi il seguente comando viene eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="1bf60-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="1bf60-128">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> prima i delimitatori di percorso non consente l'escape di classe e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="1bf60-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="1bf60-129">Il risultato di passare l'URL dannoso per <xref:System.Uri?displayProperty=nameWithType> costruttore di classe nell'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="1bf60-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="1bf60-130">Per non delimitatori di percorso con codifica percentuale di caratteri di escape annullare utilizzando l'opzione di configurazione schemeSettings per uno schema specifico, è possibile modificare questo comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="1bf60-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1bf60-131">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bf60-131">Configuration Files</span></span>  
 <span data-ttu-id="1bf60-132">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="1bf60-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bf60-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bf60-133">Example</span></span>  
 <span data-ttu-id="1bf60-134">Nell'esempio seguente viene mostrata una configurazione utilizzata per la <xref:System.Uri> classe che rimuove tutte le impostazioni dello schema per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="1bf60-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bf60-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bf60-135">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="1bf60-136">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="1bf60-136">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
