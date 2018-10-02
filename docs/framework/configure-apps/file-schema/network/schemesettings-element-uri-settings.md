---
title: '&lt;schemeSettings&gt; (impostazioni Uri)'
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 76ca5acc22eca07d372a2964cf3a6df4ea3b58d5
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48025308"
---
# <a name="ltschemesettingsgt-element-uri-settings"></a><span data-ttu-id="55138-102">&lt;schemeSettings&gt; (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="55138-102">&lt;schemeSettings&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="55138-103">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="55138-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="55138-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="55138-104">\<configuration></span></span>  
<span data-ttu-id="55138-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="55138-105">\<uri></span></span>  
<span data-ttu-id="55138-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="55138-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55138-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55138-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55138-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="55138-108">Attributes and Elements</span></span>  
 <span data-ttu-id="55138-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="55138-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55138-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="55138-110">Attributes</span></span>  
 <span data-ttu-id="55138-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="55138-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="55138-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="55138-112">Child Elements</span></span>  
  
|<span data-ttu-id="55138-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="55138-113">**Element**</span></span>|<span data-ttu-id="55138-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="55138-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="55138-115">add</span><span class="sxs-lookup"><span data-stu-id="55138-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="55138-116">Aggiunge un'impostazione di schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="55138-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="55138-117">clear</span><span class="sxs-lookup"><span data-stu-id="55138-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="55138-118">Cancella tutte le impostazioni di schema esistenti.</span><span class="sxs-lookup"><span data-stu-id="55138-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="55138-119">remove</span><span class="sxs-lookup"><span data-stu-id="55138-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="55138-120">Rimuove un'impostazione di schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="55138-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="55138-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="55138-121">Parent Elements</span></span>  
  
|<span data-ttu-id="55138-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="55138-122">**Element**</span></span>|<span data-ttu-id="55138-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="55138-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="55138-124">URI</span><span class="sxs-lookup"><span data-stu-id="55138-124">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="55138-125">Contiene le impostazioni che specificano come .NET Framework gestisce gli indirizzi web espressi tramite uniform resource identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="55138-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55138-126">Note</span><span class="sxs-lookup"><span data-stu-id="55138-126">Remarks</span></span>  
 <span data-ttu-id="55138-127">Per impostazione predefinita, il <xref:System.Uri?displayProperty=nameWithType> delimitatori di percorso con codifica percentuale non consente l'escape di classe prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="55138-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="55138-128">È stato implementato come un meccanismo di protezione contro gli attacchi simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="55138-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="55138-129">Se viene passato questo URI lungo i moduli non gestiscono percento codificati in caratteri correttamente, potrebbero verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="55138-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="55138-130">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> prima i delimitatori di percorso non consente l'escape di classi e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="55138-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="55138-131">Il risultato di passare l'URL dannoso a <xref:System.Uri?displayProperty=nameWithType> costruttore di classe nell'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="55138-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="55138-132">Possibile è possibile modificare questo comportamento predefinito per non i delimitatori del percorso con codifica percentuale ONU-escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="55138-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="55138-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="55138-133">Configuration Files</span></span>  
 <span data-ttu-id="55138-134">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="55138-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55138-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="55138-135">Example</span></span>  
 <span data-ttu-id="55138-136">Nell'esempio seguente mostra una configurazione usata dal <xref:System.Uri> classe per il supporto non escape delimitatori di percorso codificato in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="55138-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="55138-137">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="55138-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="55138-138">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="55138-138">Namespace</span></span>|<span data-ttu-id="55138-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="55138-139">System</span></span>|  
|<span data-ttu-id="55138-140">Nome di schema</span><span class="sxs-lookup"><span data-stu-id="55138-140">Schema Name</span></span>||  
|<span data-ttu-id="55138-141">File di convalida</span><span class="sxs-lookup"><span data-stu-id="55138-141">Validation File</span></span>||  
|<span data-ttu-id="55138-142">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="55138-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="55138-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55138-143">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="55138-144">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="55138-144">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
