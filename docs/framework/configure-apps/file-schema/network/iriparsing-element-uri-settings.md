---
title: '&lt;iriParsing&gt; elemento (impostazioni Uri)'
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f05f7e35d69f789d3ebb371689aafbc84004b732
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743303"
---
# <a name="ltiriparsinggt-element-uri-settings"></a><span data-ttu-id="d6bb3-102">&lt;iriParsing&gt; elemento (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="d6bb3-102">&lt;iriParsing&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="d6bb3-103">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="d6bb3-104">Gerarchia dello schema</span><span class="sxs-lookup"><span data-stu-id="d6bb3-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="d6bb3-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="d6bb3-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="d6bb3-106">\<URI > elemento (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="d6bb3-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="d6bb3-107">\<iriParsing ></span><span class="sxs-lookup"><span data-stu-id="d6bb3-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="d6bb3-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6bb3-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6bb3-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="d6bb3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d6bb3-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6bb3-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="d6bb3-111">Attributes</span></span>  
  
|<span data-ttu-id="d6bb3-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d6bb3-112">**Element**</span></span>|<span data-ttu-id="d6bb3-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d6bb3-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="d6bb3-114">Specifica se è abilitata l'analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="d6bb3-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6bb3-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d6bb3-116">Child Elements</span></span>  
 <span data-ttu-id="d6bb3-117">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d6bb3-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6bb3-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d6bb3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d6bb3-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="d6bb3-119">**Element**</span></span>|<span data-ttu-id="d6bb3-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d6bb3-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d6bb3-121">URI</span><span class="sxs-lookup"><span data-stu-id="d6bb3-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="d6bb3-122">Contiene le impostazioni che specificano come .NET Framework gestisce gli indirizzi web espressi tramite uniform resource identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="d6bb3-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6bb3-123">Note</span><span class="sxs-lookup"><span data-stu-id="d6bb3-123">Remarks</span></span>  
 <span data-ttu-id="d6bb3-124">Esistente <xref:System.Uri> classe è stata estesa in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="d6bb3-125">3.0 SP1 e 2.0 SP1 per fornire supporto per gli identificatori IRI (International Resource) e IDN (Internationalized Domain nomi).</span><span class="sxs-lookup"><span data-stu-id="d6bb3-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="d6bb3-126">Gli utenti non visualizzeranno qualsiasi modifica rispetto al comportamento di .NET Framework 2.0 a meno che non consentono in modo specifico IRI e IDN supportano.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="d6bb3-127">Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="d6bb3-128">Per abilitare il supporto per IRI, sono necessarie le seguenti due modifiche:</span><span class="sxs-lookup"><span data-stu-id="d6bb3-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="d6bb3-129">Aggiungere la riga seguente al file Machine. config nella directory di .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="d6bb3-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="d6bb3-130">Specificare se applicare le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="d6bb3-131">A questo scopo, è possibile usare il file machine.config o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="d6bb3-132">Abilitazione dell'analisi IRI (iriParsing abilitato = `true`) consentirà la normalizzazione e regole di controllo in base alle IRI più recente dei caratteri nella RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="d6bb3-133">Il valore predefinito è `false` e la normalizzazione e i caratteri di controllo in base a RFC 2396 e RFC 3986 (per i valori letterali IPv6).</span><span class="sxs-lookup"><span data-stu-id="d6bb3-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="d6bb3-134">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d6bb3-134">Configuration Files</span></span>  
 <span data-ttu-id="d6bb3-135">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d6bb3-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6bb3-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6bb3-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d6bb3-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6bb3-137">Description</span></span>  
 <span data-ttu-id="d6bb3-138">Nell'esempio seguente viene mostrata una configurazione utilizzata per la <xref:System.Uri> classe per supportare l'analisi IRI e i nomi IDN.</span><span class="sxs-lookup"><span data-stu-id="d6bb3-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d6bb3-139">Codice</span><span class="sxs-lookup"><span data-stu-id="d6bb3-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6bb3-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6bb3-140">See Also</span></span>  
 <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="d6bb3-141">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="d6bb3-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
