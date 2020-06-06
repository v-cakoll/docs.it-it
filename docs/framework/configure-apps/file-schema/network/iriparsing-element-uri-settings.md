---
title: Elemento <iriParsing> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698101"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="af324-102">Elemento \<iriParsing> (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="af324-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="af324-103">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="af324-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**  
  
## <a name="syntax"></a><span data-ttu-id="af324-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af324-104">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af324-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="af324-105">Attributes and Elements</span></span>  
 <span data-ttu-id="af324-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="af324-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af324-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="af324-107">Attributes</span></span>  
  
|<span data-ttu-id="af324-108">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af324-108">**Element**</span></span>|<span data-ttu-id="af324-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="af324-109">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="af324-110">Specifica se è abilitata l'analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="af324-110">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="af324-111">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="af324-111">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af324-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="af324-112">Child Elements</span></span>  
 <span data-ttu-id="af324-113">nessuno</span><span class="sxs-lookup"><span data-stu-id="af324-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af324-114">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="af324-114">Parent Elements</span></span>  
  
|<span data-ttu-id="af324-115">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="af324-115">**Element**</span></span>|<span data-ttu-id="af324-116">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="af324-116">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="af324-117">URI</span><span class="sxs-lookup"><span data-stu-id="af324-117">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="af324-118">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="af324-118">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af324-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="af324-119">Remarks</span></span>  
 <span data-ttu-id="af324-120">La <xref:System.Uri> classe esistente è stata estesa in .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="af324-120">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="af324-121">3,0 SP1 e 2,0 SP1 per fornire supporto per gli identificatori di risorse internazionali (IRI) e i nomi di dominio internazionali (IDN).</span><span class="sxs-lookup"><span data-stu-id="af324-121">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="af324-122">Gli utenti correnti non vedranno alcuna modifica rispetto al comportamento di .NET Framework 2,0, a meno che non vengano specificamente abilitati il supporto di IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="af324-122">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="af324-123">Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af324-123">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="af324-124">Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="af324-124">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="af324-125">Aggiungere la riga seguente al file Machine. config nella directory .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="af324-125">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="af324-126">Consente di specificare se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="af324-126">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="af324-127">A questo scopo, è possibile usare il file machine.config o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="af324-127">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="af324-128">L'abilitazione dell'analisi IRI (iriParsing enabled = `true` ) consente di eseguire la normalizzazione e il controllo dei caratteri in base alle regole IRI più recenti nella specifica RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="af324-128">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="af324-129">Il valore predefinito è `false` e effettuerà la normalizzazione e il controllo dei caratteri in base a rfc 2396 e rfc 3986 (per i valori letterali IPv6).</span><span class="sxs-lookup"><span data-stu-id="af324-129">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="af324-130">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="af324-130">Configuration Files</span></span>  
 <span data-ttu-id="af324-131">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="af324-131">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af324-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="af324-132">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="af324-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af324-133">Description</span></span>  
 <span data-ttu-id="af324-134">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla <xref:System.Uri> classe per supportare l'analisi IRI e i nomi IDN.</span><span class="sxs-lookup"><span data-stu-id="af324-134">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="af324-135">Codice</span><span class="sxs-lookup"><span data-stu-id="af324-135">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af324-136">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="af324-136">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="af324-137">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="af324-137">Network Settings Schema</span></span>](index.md)
