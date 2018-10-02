---
title: '&lt;Cancella&gt; (elemento) per schemeSettings (impostazioni Uri)'
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f0daa689ba09fa39ffe0f38d769112f0f095592a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028040"
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="442ff-102">&lt;Cancella&gt; (elemento) per schemeSettings (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="442ff-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="442ff-103">Cancella tutte le impostazioni di schema esistenti.</span><span class="sxs-lookup"><span data-stu-id="442ff-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="442ff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="442ff-104">\<configuration></span></span>  
<span data-ttu-id="442ff-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="442ff-105">\<uri></span></span>  
<span data-ttu-id="442ff-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="442ff-106">\<schemeSettings></span></span>  
<span data-ttu-id="442ff-107">\<clear ></span><span class="sxs-lookup"><span data-stu-id="442ff-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="442ff-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="442ff-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="442ff-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="442ff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="442ff-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="442ff-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="442ff-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="442ff-111">Attributes</span></span>  
 <span data-ttu-id="442ff-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="442ff-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="442ff-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="442ff-113">Child Elements</span></span>  
 <span data-ttu-id="442ff-114">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="442ff-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="442ff-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="442ff-115">Parent Elements</span></span>  
  
|<span data-ttu-id="442ff-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="442ff-116">Element</span></span>|<span data-ttu-id="442ff-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="442ff-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="442ff-118">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="442ff-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="442ff-119">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="442ff-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="442ff-120">Note</span><span class="sxs-lookup"><span data-stu-id="442ff-120">Remarks</span></span>  
 <span data-ttu-id="442ff-121">Per impostazione predefinita, il <xref:System.Uri?displayProperty=nameWithType> delimitatori di percorso con codifica percentuale non consente l'escape di classe prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="442ff-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="442ff-122">È stato implementato come un meccanismo di protezione contro gli attacchi simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="442ff-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="442ff-123">Se viene passato questo URI lungo i moduli non gestiscono percento codificati in caratteri correttamente, potrebbero verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="442ff-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="442ff-124">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> prima i delimitatori di percorso non consente l'escape di classi e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="442ff-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="442ff-125">Il risultato di passare l'URL dannoso a <xref:System.Uri?displayProperty=nameWithType> costruttore di classe nell'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="442ff-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="442ff-126">Possibile è possibile modificare questo comportamento predefinito per non i delimitatori del percorso con codifica percentuale ONU-escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="442ff-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="442ff-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="442ff-127">Configuration Files</span></span>  
 <span data-ttu-id="442ff-128">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="442ff-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="442ff-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="442ff-129">Example</span></span>  
 <span data-ttu-id="442ff-130">Nell'esempio seguente mostra una configurazione usata dal <xref:System.Uri> classe che cancella tutte le impostazioni di schema e quindi aggiunge il supporto per non eseguire l'escape delimitatori di percorso codificato in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="442ff-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="442ff-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="442ff-131">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="442ff-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="442ff-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
