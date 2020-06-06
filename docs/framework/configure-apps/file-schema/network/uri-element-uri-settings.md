---
title: Elemento <uri> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697445"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="879a8-102">Elemento \<uri> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="879a8-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="879a8-103">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="879a8-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<uri>**  
  
## <a name="syntax"></a><span data-ttu-id="879a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="879a8-104">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="879a8-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="879a8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="879a8-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="879a8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="879a8-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="879a8-107">Attributes</span></span>  
 <span data-ttu-id="879a8-108">No.</span><span class="sxs-lookup"><span data-stu-id="879a8-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="879a8-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="879a8-109">Child Elements</span></span>  
  
|<span data-ttu-id="879a8-110">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="879a8-110">**Element**</span></span>|<span data-ttu-id="879a8-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="879a8-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="879a8-112">IDN</span><span class="sxs-lookup"><span data-stu-id="879a8-112">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="879a8-113">Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="879a8-113">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="879a8-114">iriParsing</span><span class="sxs-lookup"><span data-stu-id="879a8-114">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="879a8-115">Specifica se viene applicata l'analisi IRI (International Resource Identifier) a <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="879a8-115">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="879a8-116">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="879a8-116">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="879a8-117">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="879a8-117">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="879a8-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="879a8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="879a8-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="879a8-119">**Element**</span></span>|<span data-ttu-id="879a8-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="879a8-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="879a8-121">configurazione</span><span class="sxs-lookup"><span data-stu-id="879a8-121">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="879a8-122">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="879a8-122">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="879a8-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="879a8-123">Remarks</span></span>  
 <span data-ttu-id="879a8-124">L' `uri` elemento contiene le impostazioni per i membri della <xref:System.Uri> classe utilizzata dalle classi nello <xref:System.Net> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="879a8-124">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="879a8-125">Le impostazioni configurano il supporto per IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="879a8-125">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="879a8-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="879a8-126">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="879a8-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="879a8-127">Description</span></span>  
 <span data-ttu-id="879a8-128">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla <xref:System.Uri> classe per supportare l'analisi IRI e i nomi IDN.</span><span class="sxs-lookup"><span data-stu-id="879a8-128">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="879a8-129">Nell'esempio vengono cancellate anche tutte le impostazioni dello schema e viene aggiunto il supporto per non eseguire l'escape dei delimitatori di percorso codificati in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="879a8-129">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="879a8-130">Codice</span><span class="sxs-lookup"><span data-stu-id="879a8-130">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="879a8-131">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="879a8-131">See also</span></span>

- [<span data-ttu-id="879a8-132">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="879a8-132">Network Settings Schema</span></span>](index.md)
