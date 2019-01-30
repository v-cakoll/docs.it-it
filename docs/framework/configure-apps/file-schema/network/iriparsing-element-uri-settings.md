---
title: Elemento <iriParsing> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: a4d4df8c214efb955f8f9d6678aaf8d56de71ebc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256656"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="795ae-102">\<iriParsing > (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="795ae-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="795ae-103">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="795ae-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="795ae-104">Gerarchia dello schema</span><span class="sxs-lookup"><span data-stu-id="795ae-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="795ae-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="795ae-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="795ae-106">\<URI > (impostazioni Uri)</span><span class="sxs-lookup"><span data-stu-id="795ae-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="795ae-107">\<iriParsing></span><span class="sxs-lookup"><span data-stu-id="795ae-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="795ae-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="795ae-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="795ae-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="795ae-109">Attributes and Elements</span></span>  
 <span data-ttu-id="795ae-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="795ae-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="795ae-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="795ae-111">Attributes</span></span>  
  
|<span data-ttu-id="795ae-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="795ae-112">**Element**</span></span>|<span data-ttu-id="795ae-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="795ae-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="795ae-114">Specifica se è abilitata l'analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="795ae-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="795ae-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="795ae-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="795ae-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="795ae-116">Child Elements</span></span>  
 <span data-ttu-id="795ae-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="795ae-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="795ae-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="795ae-118">Parent Elements</span></span>  
  
|<span data-ttu-id="795ae-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="795ae-119">**Element**</span></span>|<span data-ttu-id="795ae-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="795ae-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="795ae-121">uri</span><span class="sxs-lookup"><span data-stu-id="795ae-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="795ae-122">Contiene le impostazioni che specificano come .NET Framework gestisce gli indirizzi web espressi tramite uniform resource identifier (URI).</span><span class="sxs-lookup"><span data-stu-id="795ae-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="795ae-123">Note</span><span class="sxs-lookup"><span data-stu-id="795ae-123">Remarks</span></span>  
 <span data-ttu-id="795ae-124">L'oggetto esistente <xref:System.Uri> classe è stata estesa in .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="795ae-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="795ae-125">3.0 SP1 e 2.0 SP1 per fornire supporto per gli identificatori IRI (International Resource) e IDN (Internationalized Domain nomi).</span><span class="sxs-lookup"><span data-stu-id="795ae-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="795ae-126">Gli utenti correnti non noteranno cambiamenti rispetto al comportamento di .NET Framework 2.0 a meno che non consentono in modo specifico gli IRI e IDN supportano.</span><span class="sxs-lookup"><span data-stu-id="795ae-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="795ae-127">Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="795ae-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="795ae-128">Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="795ae-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="795ae-129">Aggiungere la riga seguente al file Machine. config nella directory di .NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="795ae-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="795ae-130">Specificare se le regole di analisi degli IRI deve essere applicato.</span><span class="sxs-lookup"><span data-stu-id="795ae-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="795ae-131">A questo scopo, è possibile usare il file machine.config o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="795ae-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="795ae-132">Attivando l'analisi IRI (iriParsing attivato = `true`) eseguirà la normalizzazione e regole di carattere di controllo in base a IRI più recenti nella specifica RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="795ae-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="795ae-133">Il valore predefinito è `false` e la normalizzazione e i caratteri di controllo in base alla RFC 2396 e RFC 3986 (per i valori letterali IPv6).</span><span class="sxs-lookup"><span data-stu-id="795ae-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="795ae-134">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="795ae-134">Configuration Files</span></span>  
 <span data-ttu-id="795ae-135">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="795ae-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="795ae-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="795ae-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="795ae-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="795ae-137">Description</span></span>  
 <span data-ttu-id="795ae-138">Nell'esempio seguente mostra una configurazione usata dal <xref:System.Uri> classe per supportare l'analisi IRI e IDN nomi.</span><span class="sxs-lookup"><span data-stu-id="795ae-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="795ae-139">Codice</span><span class="sxs-lookup"><span data-stu-id="795ae-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="795ae-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="795ae-140">See also</span></span>
- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="795ae-141">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="795ae-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
