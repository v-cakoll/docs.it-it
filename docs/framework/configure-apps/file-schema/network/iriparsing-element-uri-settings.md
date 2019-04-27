---
title: Elemento <iriParsing> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 7033f4dcda7d2fe73310ae0d36d9b05c090d13d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674519"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="53905-102">\<iriParsing > (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="53905-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="53905-103">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="53905-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="53905-104">Gerarchia dello schema</span><span class="sxs-lookup"><span data-stu-id="53905-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="53905-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="53905-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="53905-106">\<URI > (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="53905-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="53905-107">\<iriParsing></span><span class="sxs-lookup"><span data-stu-id="53905-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="53905-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53905-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53905-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="53905-109">Attributes and Elements</span></span>  
 <span data-ttu-id="53905-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="53905-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53905-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="53905-111">Attributes</span></span>  
  
|<span data-ttu-id="53905-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="53905-112">**Element**</span></span>|<span data-ttu-id="53905-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="53905-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="53905-114">Specifica se è abilitata l'analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="53905-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="53905-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="53905-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53905-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="53905-116">Child Elements</span></span>  
 <span data-ttu-id="53905-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="53905-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53905-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="53905-118">Parent Elements</span></span>  
  
|<span data-ttu-id="53905-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="53905-119">**Element**</span></span>|<span data-ttu-id="53905-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="53905-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="53905-121">uri</span><span class="sxs-lookup"><span data-stu-id="53905-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="53905-122">Contiene le impostazioni che specificano come .NET Framework gestisce gli indirizzi web espressi tramite uniform resource identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="53905-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53905-123">Note</span><span class="sxs-lookup"><span data-stu-id="53905-123">Remarks</span></span>  
 <span data-ttu-id="53905-124">L'oggetto esistente <xref:System.Uri> classe è stata estesa in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="53905-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="53905-125">3.0 SP1 e 2.0 SP1 per fornire supporto per gli identificatori IRI (International Resource) e IDN (Internationalized Domain nomi).</span><span class="sxs-lookup"><span data-stu-id="53905-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="53905-126">Gli utenti correnti non noteranno cambiamenti rispetto al comportamento di .NET Framework 2.0 a meno che non consentono in modo specifico gli IRI e IDN supportano.</span><span class="sxs-lookup"><span data-stu-id="53905-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="53905-127">Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="53905-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="53905-128">Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="53905-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="53905-129">Aggiungere la riga seguente al file Machine. config nella directory di .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="53905-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="53905-130">Specificare se le regole di analisi degli IRI deve essere applicato.</span><span class="sxs-lookup"><span data-stu-id="53905-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="53905-131">A questo scopo, è possibile usare il file machine.config o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="53905-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="53905-132">Attivando l'analisi IRI (iriParsing attivato = `true`) eseguirà la normalizzazione e regole di carattere di controllo in base a IRI più recenti nella specifica RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="53905-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="53905-133">Il valore predefinito è `false` e la normalizzazione e i caratteri di controllo in base alla RFC 2396 e RFC 3986 (per i valori letterali IPv6).</span><span class="sxs-lookup"><span data-stu-id="53905-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="53905-134">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="53905-134">Configuration Files</span></span>  
 <span data-ttu-id="53905-135">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="53905-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53905-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="53905-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="53905-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53905-137">Description</span></span>  
 <span data-ttu-id="53905-138">Nell'esempio seguente mostra una configurazione usata dal <xref:System.Uri> classe per supportare l'analisi IRI e IDN nomi.</span><span class="sxs-lookup"><span data-stu-id="53905-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="53905-139">Codice</span><span class="sxs-lookup"><span data-stu-id="53905-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53905-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53905-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="53905-141">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="53905-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
