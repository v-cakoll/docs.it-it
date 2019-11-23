---
title: Elemento <schemeSettings> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 498aef77a1dfd8cffcac73b704b8d1bb6df5d165
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697765"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="3b1d1-102">\<elemento > schemeSettings (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="3b1d1-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="3b1d1-103">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="3b1d1-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="3b1d1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3b1d1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3b1d1-105">&nbsp;&nbsp;[ **uri\<>** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3b1d1-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="3b1d1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<schemeSettings >**</span><span class="sxs-lookup"><span data-stu-id="3b1d1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b1d1-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b1d1-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b1d1-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3b1d1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3b1d1-109">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3b1d1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b1d1-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="3b1d1-110">Attributes</span></span>  
 <span data-ttu-id="3b1d1-111">None</span><span class="sxs-lookup"><span data-stu-id="3b1d1-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3b1d1-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3b1d1-112">Child Elements</span></span>  
  
|<span data-ttu-id="3b1d1-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="3b1d1-113">**Element**</span></span>|<span data-ttu-id="3b1d1-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3b1d1-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3b1d1-115">add</span><span class="sxs-lookup"><span data-stu-id="3b1d1-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="3b1d1-116">Aggiunge un'impostazione dello schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="3b1d1-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="3b1d1-117">clear</span><span class="sxs-lookup"><span data-stu-id="3b1d1-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="3b1d1-118">Cancella tutte le impostazioni dello schema esistente.</span><span class="sxs-lookup"><span data-stu-id="3b1d1-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="3b1d1-119">remove</span><span class="sxs-lookup"><span data-stu-id="3b1d1-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="3b1d1-120">Rimuove un'impostazione dello schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="3b1d1-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b1d1-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3b1d1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3b1d1-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="3b1d1-122">**Element**</span></span>|<span data-ttu-id="3b1d1-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3b1d1-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="3b1d1-124">uri</span><span class="sxs-lookup"><span data-stu-id="3b1d1-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="3b1d1-125">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="3b1d1-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b1d1-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3b1d1-126">Remarks</span></span>  
 <span data-ttu-id="3b1d1-127">Per impostazione predefinita, la classe <xref:System.Uri?displayProperty=nameWithType> Annulla il carattere di escape per la percentuale di delimitatori di percorso codificati prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="3b1d1-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="3b1d1-128">Questa operazione è stata implementata come meccanismo di sicurezza da attacchi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b1d1-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3b1d1-129">Se questo URI viene passato a moduli che non gestiscono correttamente la percentuale di caratteri codificati, potrebbe verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="3b1d1-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="3b1d1-130">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> classe First Annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="3b1d1-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="3b1d1-131">Il risultato del passaggio dell'URL dannoso precedente a <xref:System.Uri?displayProperty=nameWithType> costruttore della classe comporta l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="3b1d1-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3b1d1-132">Questo comportamento predefinito può essere modificato in modo da non delimitatore di percorso codificato con percentuale di escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="3b1d1-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3b1d1-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3b1d1-133">Configuration Files</span></span>  
 <span data-ttu-id="3b1d1-134">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3b1d1-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b1d1-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="3b1d1-135">Example</span></span>  
 <span data-ttu-id="3b1d1-136">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla classe <xref:System.Uri> per supportare il mancato escape di delimitatori di percorso con codifica percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="3b1d1-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="3b1d1-137">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="3b1d1-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="3b1d1-138">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3b1d1-138">Namespace</span></span>|<span data-ttu-id="3b1d1-139">System</span><span class="sxs-lookup"><span data-stu-id="3b1d1-139">System</span></span>|  
|<span data-ttu-id="3b1d1-140">Nome di schema</span><span class="sxs-lookup"><span data-stu-id="3b1d1-140">Schema Name</span></span>||  
|<span data-ttu-id="3b1d1-141">File di convalida</span><span class="sxs-lookup"><span data-stu-id="3b1d1-141">Validation File</span></span>||  
|<span data-ttu-id="3b1d1-142">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="3b1d1-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="3b1d1-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b1d1-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="3b1d1-144">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="3b1d1-144">Network Settings Schema</span></span>](index.md)
