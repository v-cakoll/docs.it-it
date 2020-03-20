---
title: Elemento <schemeSettings> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154647"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="99e22-102">\<Elemento schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="99e22-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="99e22-103">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="99e22-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="99e22-104">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="99e22-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="99e22-105">&nbsp;&nbsp;[**\<>uri**](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="99e22-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="99e22-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>schemeSettings**</span><span class="sxs-lookup"><span data-stu-id="99e22-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e22-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99e22-107">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99e22-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="99e22-108">Attributes and Elements</span></span>  
 <span data-ttu-id="99e22-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="99e22-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99e22-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="99e22-110">Attributes</span></span>  
 <span data-ttu-id="99e22-111">nessuno</span><span class="sxs-lookup"><span data-stu-id="99e22-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="99e22-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="99e22-112">Child Elements</span></span>  
  
|<span data-ttu-id="99e22-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="99e22-113">**Element**</span></span>|<span data-ttu-id="99e22-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="99e22-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="99e22-115">aggiungi</span><span class="sxs-lookup"><span data-stu-id="99e22-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="99e22-116">Aggiunge un'impostazione di schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="99e22-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="99e22-117">Chiaro</span><span class="sxs-lookup"><span data-stu-id="99e22-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="99e22-118">Cancella tutte le impostazioni dello schema esistenti.</span><span class="sxs-lookup"><span data-stu-id="99e22-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="99e22-119">rimozione</span><span class="sxs-lookup"><span data-stu-id="99e22-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="99e22-120">Rimuove un'impostazione di schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="99e22-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99e22-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="99e22-121">Parent Elements</span></span>  
  
|<span data-ttu-id="99e22-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="99e22-122">**Element**</span></span>|<span data-ttu-id="99e22-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="99e22-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="99e22-124">Uri</span><span class="sxs-lookup"><span data-stu-id="99e22-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="99e22-125">Contiene impostazioni che specificano il modo in cui .NET Framework gestisce gli indirizzi Web espressi utilizzando URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="99e22-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99e22-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="99e22-126">Remarks</span></span>  
 <span data-ttu-id="99e22-127">Per impostazione <xref:System.Uri?displayProperty=nameWithType> predefinita, la classe annulla l'escape dei delimitatori di percorso con codifica percentuale prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="99e22-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="99e22-128">Questo è stato implementato come un meccanismo di sicurezza contro gli attacchi come il seguente:</span><span class="sxs-lookup"><span data-stu-id="99e22-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="99e22-129">Se questo URI viene passato ai moduli che non gestiscono correttamente la percentuale di caratteri codificati, è possibile che il comando seguente venga eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="99e22-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="99e22-130">Per questo <xref:System.Uri?displayProperty=nameWithType> motivo, la classe prima annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="99e22-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="99e22-131">Il risultato del passaggio <xref:System.Uri?displayProperty=nameWithType> dell'URL dannoso sopra al costruttore di classe genera il seguente URI:</span><span class="sxs-lookup"><span data-stu-id="99e22-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="99e22-132">Questo comportamento predefinito può essere modificato per non annullare l'escape dei delimitatori di percorso con codifica percentuale utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="99e22-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="99e22-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="99e22-133">Configuration Files</span></span>  
 <span data-ttu-id="99e22-134">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="99e22-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99e22-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="99e22-135">Example</span></span>  
 <span data-ttu-id="99e22-136">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla classe per supportare la <xref:System.Uri> non escludidelimitatori di percorso con codifica percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="99e22-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="99e22-137">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="99e22-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="99e22-138">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="99e22-138">Namespace</span></span>|<span data-ttu-id="99e22-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="99e22-139">System</span></span>|  
|<span data-ttu-id="99e22-140">Schema Name</span><span class="sxs-lookup"><span data-stu-id="99e22-140">Schema Name</span></span>||  
|<span data-ttu-id="99e22-141">File di convalida</span><span class="sxs-lookup"><span data-stu-id="99e22-141">Validation File</span></span>||  
|<span data-ttu-id="99e22-142">Può essere Vuoto</span><span class="sxs-lookup"><span data-stu-id="99e22-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="99e22-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99e22-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="99e22-144">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="99e22-144">Network Settings Schema</span></span>](index.md)
