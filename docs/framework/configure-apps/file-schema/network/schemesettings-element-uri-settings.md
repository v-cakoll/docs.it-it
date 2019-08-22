---
title: Elemento <schemeSettings> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 46012b15d41422fb3357e57438e320136809ef41
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664002"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="d8b02-102">\<Elemento > schemeSettings (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="d8b02-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="d8b02-103">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="d8b02-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="d8b02-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d8b02-104">\<configuration></span></span>  
<span data-ttu-id="d8b02-105">\<uri></span><span class="sxs-lookup"><span data-stu-id="d8b02-105">\<uri></span></span>  
<span data-ttu-id="d8b02-106">\<schemeSettings></span><span class="sxs-lookup"><span data-stu-id="d8b02-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b02-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8b02-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8b02-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d8b02-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d8b02-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d8b02-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8b02-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="d8b02-110">Attributes</span></span>  
 <span data-ttu-id="d8b02-111">Nessuna</span><span class="sxs-lookup"><span data-stu-id="d8b02-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8b02-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d8b02-112">Child Elements</span></span>  
  
|<span data-ttu-id="d8b02-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d8b02-113">**Element**</span></span>|<span data-ttu-id="d8b02-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d8b02-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d8b02-115">add</span><span class="sxs-lookup"><span data-stu-id="d8b02-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="d8b02-116">Aggiunge un'impostazione dello schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="d8b02-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="d8b02-117">clear</span><span class="sxs-lookup"><span data-stu-id="d8b02-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="d8b02-118">Cancella tutte le impostazioni dello schema esistente.</span><span class="sxs-lookup"><span data-stu-id="d8b02-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="d8b02-119">remove</span><span class="sxs-lookup"><span data-stu-id="d8b02-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="d8b02-120">Rimuove un'impostazione dello schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="d8b02-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8b02-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d8b02-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d8b02-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d8b02-122">**Element**</span></span>|<span data-ttu-id="d8b02-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d8b02-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d8b02-124">uri</span><span class="sxs-lookup"><span data-stu-id="d8b02-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="d8b02-125">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="d8b02-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8b02-126">Note</span><span class="sxs-lookup"><span data-stu-id="d8b02-126">Remarks</span></span>  
 <span data-ttu-id="d8b02-127">Per impostazione predefinita, <xref:System.Uri?displayProperty=nameWithType> la classe Annulla l'escape per la percentuale di delimitatori di percorso codificati prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="d8b02-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="d8b02-128">Questa operazione è stata implementata come meccanismo di sicurezza da attacchi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8b02-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="d8b02-129">Se questo URI viene passato a moduli che non gestiscono correttamente la percentuale di caratteri codificati, potrebbe verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="d8b02-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="d8b02-130">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> First Class Annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="d8b02-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="d8b02-131">Il risultato del passaggio dell'URL dannoso precedente <xref:System.Uri?displayProperty=nameWithType> al costruttore della classe comporta l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="d8b02-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="d8b02-132">Questo comportamento predefinito può essere modificato in modo da non delimitatore di percorso codificato con percentuale di escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="d8b02-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d8b02-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d8b02-133">Configuration Files</span></span>  
 <span data-ttu-id="d8b02-134">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d8b02-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8b02-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8b02-135">Example</span></span>  
 <span data-ttu-id="d8b02-136">Nell'esempio seguente viene illustrata una configurazione utilizzata <xref:System.Uri> dalla classe per supportare la mancata evasione dei delimitatori di percorso codificati in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="d8b02-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="d8b02-137">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="d8b02-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="d8b02-138">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="d8b02-138">Namespace</span></span>|<span data-ttu-id="d8b02-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="d8b02-139">System</span></span>|  
|<span data-ttu-id="d8b02-140">Nome di schema</span><span class="sxs-lookup"><span data-stu-id="d8b02-140">Schema Name</span></span>||  
|<span data-ttu-id="d8b02-141">File di convalida</span><span class="sxs-lookup"><span data-stu-id="d8b02-141">Validation File</span></span>||  
|<span data-ttu-id="d8b02-142">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="d8b02-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="d8b02-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8b02-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="d8b02-144">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d8b02-144">Network Settings Schema</span></span>](index.md)
