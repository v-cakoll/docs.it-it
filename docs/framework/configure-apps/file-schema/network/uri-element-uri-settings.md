---
title: Elemento <uri> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697445"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="cbc31-102">\<Uri > elemento (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="cbc31-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="cbc31-103">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="cbc31-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[<span data-ttu-id="cbc31-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="cbc31-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="cbc31-105">&nbsp;&nbsp;**uri\<>**</span><span class="sxs-lookup"><span data-stu-id="cbc31-105">&nbsp;&nbsp;**\<uri>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbc31-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbc31-106">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbc31-107">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="cbc31-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cbc31-108">Le sezioni seguenti descrivono gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="cbc31-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbc31-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="cbc31-109">Attributes</span></span>  
 <span data-ttu-id="cbc31-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="cbc31-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cbc31-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="cbc31-111">Child Elements</span></span>  
  
|<span data-ttu-id="cbc31-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cbc31-112">**Element**</span></span>|<span data-ttu-id="cbc31-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cbc31-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cbc31-114">idn</span><span class="sxs-lookup"><span data-stu-id="cbc31-114">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="cbc31-115">Specifica se l'analisi IDN (Internationalized Domain Name) viene applicata ai nomi di dominio.</span><span class="sxs-lookup"><span data-stu-id="cbc31-115">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="cbc31-116">iriParsing</span><span class="sxs-lookup"><span data-stu-id="cbc31-116">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="cbc31-117">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="cbc31-117">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="cbc31-118">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="cbc31-118">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="cbc31-119">Specifica come verrà analizzato un <xref:System.Uri> per schemi specifici.</span><span class="sxs-lookup"><span data-stu-id="cbc31-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cbc31-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="cbc31-120">Parent Elements</span></span>  
  
|<span data-ttu-id="cbc31-121">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="cbc31-121">**Element**</span></span>|<span data-ttu-id="cbc31-122">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cbc31-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cbc31-123">configuration</span><span class="sxs-lookup"><span data-stu-id="cbc31-123">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="cbc31-124">Contiene le impostazioni per tutti gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="cbc31-124">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbc31-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cbc31-125">Remarks</span></span>  
 <span data-ttu-id="cbc31-126">L'elemento `uri` contiene le impostazioni per i membri della classe <xref:System.Uri> utilizzata dalle classi nello spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="cbc31-126">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="cbc31-127">Le impostazioni configurano il supporto per IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="cbc31-127">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbc31-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbc31-128">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cbc31-129">description</span><span class="sxs-lookup"><span data-stu-id="cbc31-129">Description</span></span>  
 <span data-ttu-id="cbc31-130">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla classe <xref:System.Uri> per supportare l'analisi IRI e i nomi IDN.</span><span class="sxs-lookup"><span data-stu-id="cbc31-130">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="cbc31-131">Nell'esempio vengono cancellate anche tutte le impostazioni dello schema e viene aggiunto il supporto per non eseguire l'escape dei delimitatori di percorso codificati in percentuale per lo schema http.</span><span class="sxs-lookup"><span data-stu-id="cbc31-131">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cbc31-132">Codice</span><span class="sxs-lookup"><span data-stu-id="cbc31-132">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cbc31-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbc31-133">See also</span></span>

- [<span data-ttu-id="cbc31-134">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="cbc31-134">Network Settings Schema</span></span>](index.md)
