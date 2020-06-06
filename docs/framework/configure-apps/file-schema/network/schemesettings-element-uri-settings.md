---
title: Elemento <schemeSettings> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: c745c90bb61b9ee393687d7f6db4fd11565c7dc7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154647"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="a87a3-102">Elemento \<schemeSettings> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="a87a3-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="a87a3-103">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="a87a3-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="a87a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a87a3-104">Syntax</span></span>  
  
```xml  
<schemeSettings>
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a87a3-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a87a3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a87a3-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a87a3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a87a3-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="a87a3-107">Attributes</span></span>  
 <span data-ttu-id="a87a3-108">nessuno</span><span class="sxs-lookup"><span data-stu-id="a87a3-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a87a3-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a87a3-109">Child Elements</span></span>  
  
|<span data-ttu-id="a87a3-110">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a87a3-110">**Element**</span></span>|<span data-ttu-id="a87a3-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a87a3-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a87a3-112">add</span><span class="sxs-lookup"><span data-stu-id="a87a3-112">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="a87a3-113">Aggiunge un'impostazione dello schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="a87a3-113">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="a87a3-114">deselezionare</span><span class="sxs-lookup"><span data-stu-id="a87a3-114">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="a87a3-115">Cancella tutte le impostazioni dello schema esistente.</span><span class="sxs-lookup"><span data-stu-id="a87a3-115">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="a87a3-116">remove</span><span class="sxs-lookup"><span data-stu-id="a87a3-116">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="a87a3-117">Rimuove un'impostazione dello schema per un nome di schema.</span><span class="sxs-lookup"><span data-stu-id="a87a3-117">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a87a3-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a87a3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a87a3-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a87a3-119">**Element**</span></span>|<span data-ttu-id="a87a3-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a87a3-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a87a3-121">URI</span><span class="sxs-lookup"><span data-stu-id="a87a3-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="a87a3-122">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="a87a3-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a87a3-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="a87a3-123">Remarks</span></span>  
 <span data-ttu-id="a87a3-124">Per impostazione predefinita, la <xref:System.Uri?displayProperty=nameWithType> classe Annulla l'escape per la percentuale di delimitatori di percorso codificati prima di eseguire la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="a87a3-124">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="a87a3-125">Questa operazione è stata implementata come meccanismo di sicurezza da attacchi come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="a87a3-125">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a87a3-126">Se questo URI viene passato a moduli che non gestiscono correttamente la percentuale di caratteri codificati, potrebbe verificarsi il seguente comando eseguito dal server:</span><span class="sxs-lookup"><span data-stu-id="a87a3-126">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="a87a3-127">Per questo motivo, <xref:System.Uri?displayProperty=nameWithType> First Class Annulla l'escape dei delimitatori di percorso e quindi applica la compressione del percorso.</span><span class="sxs-lookup"><span data-stu-id="a87a3-127">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="a87a3-128">Il risultato del passaggio dell'URL dannoso precedente al <xref:System.Uri?displayProperty=nameWithType> costruttore della classe comporta l'URI seguente:</span><span class="sxs-lookup"><span data-stu-id="a87a3-128">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a87a3-129">Questo comportamento predefinito può essere modificato in modo da non delimitatore di percorso codificato con percentuale di escape utilizzando l'opzione di configurazione schemeSettings per uno schema specifico.</span><span class="sxs-lookup"><span data-stu-id="a87a3-129">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a87a3-130">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="a87a3-130">Configuration Files</span></span>  
 <span data-ttu-id="a87a3-131">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a87a3-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a87a3-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="a87a3-132">Example</span></span>  
 <span data-ttu-id="a87a3-133">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla <xref:System.Uri> classe per supportare la mancata evasione dei delimitatori di percorso codificati in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="a87a3-133">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="a87a3-134">Informazioni sull'elemento</span><span class="sxs-lookup"><span data-stu-id="a87a3-134">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="a87a3-135">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a87a3-135">Namespace</span></span>|<span data-ttu-id="a87a3-136">Sistema</span><span class="sxs-lookup"><span data-stu-id="a87a3-136">System</span></span>|  
|<span data-ttu-id="a87a3-137">Schema Name</span><span class="sxs-lookup"><span data-stu-id="a87a3-137">Schema Name</span></span>||  
|<span data-ttu-id="a87a3-138">File di convalida</span><span class="sxs-lookup"><span data-stu-id="a87a3-138">Validation File</span></span>||  
|<span data-ttu-id="a87a3-139">Può essere vuoto</span><span class="sxs-lookup"><span data-stu-id="a87a3-139">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="a87a3-140">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a87a3-140">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="a87a3-141">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="a87a3-141">Network Settings Schema</span></span>](index.md)
