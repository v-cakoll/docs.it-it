---
title: Elemento <Uri> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 80d71da5ca680872e4948fa8ff135fbbdf08cffe
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663971"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="fcdf0-102">\<Elemento > URI (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="fcdf0-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="fcdf0-103">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="fcdf0-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="fcdf0-104">Gerarchia dello schema</span><span class="sxs-lookup"><span data-stu-id="fcdf0-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="fcdf0-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="fcdf0-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="fcdf0-106">\<uri></span><span class="sxs-lookup"><span data-stu-id="fcdf0-106">\<uri></span></span>](uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="fcdf0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcdf0-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcdf0-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fcdf0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fcdf0-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcdf0-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="fcdf0-110">Attributes</span></span>  
 <span data-ttu-id="fcdf0-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fcdf0-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fcdf0-112">Child Elements</span></span>  
  
|<span data-ttu-id="fcdf0-113">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fcdf0-113">**Element**</span></span>|<span data-ttu-id="fcdf0-114">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fcdf0-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fcdf0-115">idn</span><span class="sxs-lookup"><span data-stu-id="fcdf0-115">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="fcdf0-116">Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="fcdf0-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="fcdf0-117">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="fcdf0-118">Specifica se viene applicata l'analisi IRI (International Resource Identifier) a <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="fcdf0-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="fcdf0-119">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="fcdf0-120">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcdf0-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fcdf0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fcdf0-122">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="fcdf0-122">**Element**</span></span>|<span data-ttu-id="fcdf0-123">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="fcdf0-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fcdf0-124">configuration</span><span class="sxs-lookup"><span data-stu-id="fcdf0-124">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="fcdf0-125">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcdf0-126">Note</span><span class="sxs-lookup"><span data-stu-id="fcdf0-126">Remarks</span></span>  
 <span data-ttu-id="fcdf0-127">L' `uri` elemento contiene le impostazioni per i membri <xref:System.Uri> della classe <xref:System.Net> utilizzata dalle classi nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="fcdf0-128">Le impostazioni configurano il supporto per IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcdf0-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcdf0-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="fcdf0-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcdf0-130">Description</span></span>  
 <span data-ttu-id="fcdf0-131">Nell'esempio seguente viene illustrata una configurazione utilizzata <xref:System.Uri> dalla classe per supportare l'analisi IRI e i nomi IDN.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="fcdf0-132">Nell'esempio vengono cancellate anche tutte le impostazioni dello schema e viene aggiunto il supporto per non eseguire l'escape dei delimitatori di percorso codificati in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="fcdf0-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fcdf0-133">Codice</span><span class="sxs-lookup"><span data-stu-id="fcdf0-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcdf0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcdf0-134">See also</span></span>

- [<span data-ttu-id="fcdf0-135">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="fcdf0-135">Network Settings Schema</span></span>](index.md)
