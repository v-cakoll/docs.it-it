---
title: Elemento <iriParsing> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 2c99edf2f1a03e0e510858c106cad43b0eaa27b4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664080"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="dc632-102">\<Elemento > iriParsing (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="dc632-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="dc632-103">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="dc632-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="dc632-104">Gerarchia dello schema</span><span class="sxs-lookup"><span data-stu-id="dc632-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="dc632-105">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="dc632-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="dc632-106">\<Elemento > URI (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="dc632-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="dc632-107">\<iriParsing></span><span class="sxs-lookup"><span data-stu-id="dc632-107">\<iriParsing></span></span>](iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="dc632-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc632-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc632-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dc632-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dc632-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dc632-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc632-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="dc632-111">Attributes</span></span>  
  
|<span data-ttu-id="dc632-112">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="dc632-112">**Element**</span></span>|<span data-ttu-id="dc632-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dc632-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="dc632-114">Specifica se è abilitata l'analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="dc632-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="dc632-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="dc632-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc632-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dc632-116">Child Elements</span></span>  
 <span data-ttu-id="dc632-117">Nessuna</span><span class="sxs-lookup"><span data-stu-id="dc632-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc632-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dc632-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dc632-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="dc632-119">**Element**</span></span>|<span data-ttu-id="dc632-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="dc632-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="dc632-121">uri</span><span class="sxs-lookup"><span data-stu-id="dc632-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="dc632-122">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="dc632-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc632-123">Note</span><span class="sxs-lookup"><span data-stu-id="dc632-123">Remarks</span></span>  
 <span data-ttu-id="dc632-124">La classe <xref:System.Uri> esistente è stata estesa in .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="dc632-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="dc632-125">3,0 SP1 e 2,0 SP1 per fornire supporto per gli identificatori di risorse internazionali (IRI) e i nomi di dominio internazionali (IDN).</span><span class="sxs-lookup"><span data-stu-id="dc632-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="dc632-126">Gli utenti correnti non vedranno alcuna modifica rispetto al comportamento di .NET Framework 2,0, a meno che non vengano specificamente abilitati il supporto di IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="dc632-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="dc632-127">Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dc632-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="dc632-128">Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc632-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="dc632-129">Aggiungere la riga seguente al file Machine. config nella directory .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="dc632-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="dc632-130">Consente di specificare se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="dc632-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="dc632-131">A questo scopo, è possibile usare il file machine.config o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="dc632-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="dc632-132">L'abilitazione dell'analisi IRI (iriParsing `true`Enabled =) consente di eseguire la normalizzazione e il controllo dei caratteri in base alle regole IRI più recenti nella specifica RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="dc632-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="dc632-133">Il valore predefinito è `false` e effettuerà la normalizzazione e il controllo dei caratteri in base a RFC 2396 e RFC 3986 (per i valori letterali IPv6).</span><span class="sxs-lookup"><span data-stu-id="dc632-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="dc632-134">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="dc632-134">Configuration Files</span></span>  
 <span data-ttu-id="dc632-135">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="dc632-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc632-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc632-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="dc632-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc632-137">Description</span></span>  
 <span data-ttu-id="dc632-138">Nell'esempio seguente viene illustrata una configurazione utilizzata <xref:System.Uri> dalla classe per supportare l'analisi IRI e i nomi IDN.</span><span class="sxs-lookup"><span data-stu-id="dc632-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="dc632-139">Codice</span><span class="sxs-lookup"><span data-stu-id="dc632-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc632-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc632-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="dc632-141">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="dc632-141">Network Settings Schema</span></span>](index.md)
