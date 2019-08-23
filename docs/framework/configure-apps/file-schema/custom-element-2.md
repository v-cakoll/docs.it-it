---
title: Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921024"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="78b3a-102">Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="78b3a-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="78b3a-103">Definisce le impostazioni per le sezioni di configurazione personalizzate <xref:System.Configuration.NameValueSectionHandler> che <xref:System.Configuration.DictionarySectionHandler> usano le classi e.</span><span class="sxs-lookup"><span data-stu-id="78b3a-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="78b3a-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="78b3a-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="78b3a-105">&nbsp;&nbsp; **\<sectionName>**</span><span class="sxs-lookup"><span data-stu-id="78b3a-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="78b3a-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="78b3a-106">Attributes</span></span>

<span data-ttu-id="78b3a-107">Nessuna</span><span class="sxs-lookup"><span data-stu-id="78b3a-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="78b3a-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="78b3a-108">Parent element</span></span>

|     | <span data-ttu-id="78b3a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78b3a-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="78b3a-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="78b3a-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="78b3a-111">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78b3a-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="78b3a-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="78b3a-112">Child elements</span></span>

|     | <span data-ttu-id="78b3a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78b3a-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="78b3a-114">aggiungere > per e [ **\<** ](add-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="78b3a-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="78b3a-115">Aggiunge le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="78b3a-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="78b3a-116">rimuovere > per e [ **\<** ](remove-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="78b3a-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="78b3a-117">Rimuove un'impostazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="78b3a-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="78b3a-118">Cancella > per e [ **\<** ](clear-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="78b3a-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="78b3a-119">Cancella tutte le impostazioni definite in precedenza in una sezione.</span><span class="sxs-lookup"><span data-stu-id="78b3a-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="78b3a-120">Note</span><span class="sxs-lookup"><span data-stu-id="78b3a-120">Remarks</span></span>

<span data-ttu-id="78b3a-121">**L'\<elemento sectionName >** è un elemento personalizzato definito da una  **\<sezione >** tag nell'  **\<elemento > configSections** .</span><span class="sxs-lookup"><span data-stu-id="78b3a-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="78b3a-122">La tabella seguente illustra il tipo di oggetto restituito dal metodo ConfigurationSettings. GetConfig per ogni gestore della sezione di configurazione:</span><span class="sxs-lookup"><span data-stu-id="78b3a-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="78b3a-123">Gestore della sezione di configurazione</span><span class="sxs-lookup"><span data-stu-id="78b3a-123">Configuration section handler</span></span>                        | <span data-ttu-id="78b3a-124">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="78b3a-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="78b3a-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="78b3a-125">Example</span></span>

<span data-ttu-id="78b3a-126">Nell'esempio seguente viene illustrato come dichiarare sezioni che utilizzano le <xref:System.Configuration.DictionarySectionHandler> classi <xref:System.Configuration.NameValueSectionHandler> e.</span><span class="sxs-lookup"><span data-stu-id="78b3a-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="78b3a-127">Il primo elemento personalizzato è  **\<dictionarySample >** , che contiene <xref:System.Configuration.DictionarySectionHandler> le impostazioni lette dalla classe nell' `System.dll` assembly.</span><span class="sxs-lookup"><span data-stu-id="78b3a-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="78b3a-128">Il secondo elemento personalizzato è  **\<section >** , che contiene <xref:System.Configuration.NameValueSectionHandler> le impostazioni lette dalla classe nell' `System.dll` assembly.</span><span class="sxs-lookup"><span data-stu-id="78b3a-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="78b3a-129">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="78b3a-129">Configuration file</span></span>

<span data-ttu-id="78b3a-130">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="78b3a-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="78b3a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78b3a-131">See also</span></span>

- [<span data-ttu-id="78b3a-132">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="78b3a-132">Configuration file schema for the .NET Framework</span></span>](index.md)
