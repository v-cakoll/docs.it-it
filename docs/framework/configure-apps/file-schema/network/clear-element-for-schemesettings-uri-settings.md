---
title: '&lt;deselezionare&gt; elemento per schemeSettings (impostazioni Uri)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a2a4841635b5d6bcaa49d024dd92241573473036
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="74cf2-102">&lt;deselezionare&gt; elemento per schemeSettings (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="74cf2-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="74cf2-103">Cancella tutte le impostazioni di schema esistenti.</span><span class="sxs-lookup"><span data-stu-id="74cf2-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="74cf2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="74cf2-104">\<configuration></span></span>  
<span data-ttu-id="74cf2-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="74cf2-105">\<uri></span></span>  
<span data-ttu-id="74cf2-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="74cf2-106">\<schemeSettings></span></span>  
<span data-ttu-id="74cf2-107">\<Deselezionare ></span><span class="sxs-lookup"><span data-stu-id="74cf2-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74cf2-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74cf2-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74cf2-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="74cf2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="74cf2-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="74cf2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74cf2-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="74cf2-111">Attributes</span></span>  
 <span data-ttu-id="74cf2-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="74cf2-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="74cf2-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="74cf2-113">Child Elements</span></span>  
 <span data-ttu-id="74cf2-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="74cf2-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74cf2-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="74cf2-115">Parent Elements</span></span>  
  
|<span data-ttu-id="74cf2-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="74cf2-116">Element</span></span>|<span data-ttu-id="74cf2-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74cf2-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74cf2-118">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="74cf2-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="74cf2-119">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="74cf2-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74cf2-120">Note</span><span class="sxs-lookup"><span data-stu-id="74cf2-120">Remarks</span></span>  
 <span data-ttu-id="74cf2-121">Per impostazione predefinita, il <xref:System.Uri?displayProperty=nameWithType> delimitatori di percorso con codifica percentuale non consente l'escape di classe prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="74cf2-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="74cf2-122">È stato implementato come un meccanismo di protezione contro gli attacchi simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="74cf2-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="74cf2-123">Se questo URI viene passato a moduli non gestiscono percentuale correttamente codificati in caratteri, potrebbe verificarsi il seguente comando viene eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="74cf2-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="74cf2-124">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> prima i delimitatori di percorso non consente l'escape di classe e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="74cf2-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="74cf2-125">Il risultato di passare l'URL dannoso per <xref:System.Uri?displayProperty=nameWithType> costruttore di classe nell'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="74cf2-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="74cf2-126">Per non delimitatori di percorso con codifica percentuale di caratteri di escape annullare utilizzando l'opzione di configurazione schemeSettings per uno schema specifico, è possibile modificare questo comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="74cf2-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="74cf2-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="74cf2-127">Configuration Files</span></span>  
 <span data-ttu-id="74cf2-128">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="74cf2-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="74cf2-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="74cf2-129">Example</span></span>  
 <span data-ttu-id="74cf2-130">Nell'esempio seguente viene mostrata una configurazione utilizzata per la <xref:System.Uri> classe che cancella tutte le impostazioni di schema e quindi aggiunge il supporto per sequenza di escape non delimitatori di percorso con codifica percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="74cf2-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74cf2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74cf2-131">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="74cf2-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="74cf2-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
