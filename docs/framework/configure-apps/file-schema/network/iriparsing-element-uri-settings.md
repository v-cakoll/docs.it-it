---
title: Elemento <iriParsing> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698101"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="4087c-102">Elemento > \<iriParsing (impostazioni URI)</span><span class="sxs-lookup"><span data-stu-id="4087c-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="4087c-103">Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="4087c-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[<span data-ttu-id="4087c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="4087c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="4087c-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4087c-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="4087c-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<iriParsing >**</span><span class="sxs-lookup"><span data-stu-id="4087c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4087c-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4087c-107">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4087c-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4087c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4087c-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4087c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4087c-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="4087c-110">Attributes</span></span>  
  
|<span data-ttu-id="4087c-111">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="4087c-111">**Element**</span></span>|<span data-ttu-id="4087c-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4087c-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="4087c-113">Specifica se è abilitata l'analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="4087c-113">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="4087c-114">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="4087c-114">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4087c-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4087c-115">Child Elements</span></span>  
 <span data-ttu-id="4087c-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="4087c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4087c-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4087c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4087c-118">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="4087c-118">**Element**</span></span>|<span data-ttu-id="4087c-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4087c-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4087c-120">uri</span><span class="sxs-lookup"><span data-stu-id="4087c-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="4087c-121">Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="4087c-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4087c-122">Note</span><span class="sxs-lookup"><span data-stu-id="4087c-122">Remarks</span></span>  
 <span data-ttu-id="4087c-123">La classe <xref:System.Uri> esistente è stata estesa in .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="4087c-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="4087c-124">3,0 SP1 e 2,0 SP1 per fornire supporto per gli identificatori di risorse internazionali (IRI) e i nomi di dominio internazionali (IDN).</span><span class="sxs-lookup"><span data-stu-id="4087c-124">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="4087c-125">Gli utenti correnti non vedranno alcuna modifica rispetto al comportamento di .NET Framework 2,0, a meno che non vengano specificamente abilitati il supporto di IRI e IDN.</span><span class="sxs-lookup"><span data-stu-id="4087c-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="4087c-126">Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4087c-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="4087c-127">Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="4087c-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="4087c-128">Aggiungere la riga seguente al file Machine. config nella directory .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="4087c-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="4087c-129">Consente di specificare se devono essere applicate le regole di analisi IRI.</span><span class="sxs-lookup"><span data-stu-id="4087c-129">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="4087c-130">A questo scopo, è possibile usare il file machine.config o il file app.config.</span><span class="sxs-lookup"><span data-stu-id="4087c-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="4087c-131">L'abilitazione dell'analisi IRI (iriParsing `true`Enabled =) consente di eseguire la normalizzazione e il controllo dei caratteri in base alle regole IRI più recenti nella specifica RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="4087c-131">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="4087c-132">Il valore predefinito è `false` e effettuerà la normalizzazione e il controllo dei caratteri in base alle specifiche RFC 2396 e RFC 3986 (per i valori letterali IPv6).</span><span class="sxs-lookup"><span data-stu-id="4087c-132">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="4087c-133">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="4087c-133">Configuration Files</span></span>  
 <span data-ttu-id="4087c-134">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4087c-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4087c-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="4087c-135">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="4087c-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4087c-136">Description</span></span>  
 <span data-ttu-id="4087c-137">Nell'esempio seguente viene illustrata una configurazione utilizzata dalla classe <xref:System.Uri> per supportare l'analisi IRI e i nomi IDN.</span><span class="sxs-lookup"><span data-stu-id="4087c-137">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4087c-138">Codice</span><span class="sxs-lookup"><span data-stu-id="4087c-138">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4087c-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4087c-139">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="4087c-140">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="4087c-140">Network Settings Schema</span></span>](index.md)
