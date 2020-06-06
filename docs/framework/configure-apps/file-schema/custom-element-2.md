---
title: Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215484"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="2bfd0-102">Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="2bfd0-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="2bfd0-103">Definisce le impostazioni per le sezioni di configurazione personalizzate che usano le <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> classi e.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a><span data-ttu-id="2bfd0-104">Attributi</span><span class="sxs-lookup"><span data-stu-id="2bfd0-104">Attributes</span></span>

<span data-ttu-id="2bfd0-105">nessuno</span><span class="sxs-lookup"><span data-stu-id="2bfd0-105">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="2bfd0-106">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="2bfd0-106">Parent element</span></span>

|     | <span data-ttu-id="2bfd0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2bfd0-107">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="2bfd0-108">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-108">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2bfd0-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2bfd0-109">Child elements</span></span>

|     | <span data-ttu-id="2bfd0-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2bfd0-110">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="2bfd0-111">[**\<add>**](add-element-for-custom-2.md)per <xref:System.Configuration.NameValueSectionHandler> e<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="2bfd0-111">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="2bfd0-112">Aggiunge le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-112">Adds custom application settings.</span></span> |
| <span data-ttu-id="2bfd0-113">[**\<remove>**](remove-element-for-custom-2.md)per <xref:System.Configuration.NameValueSectionHandler> e<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="2bfd0-113">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="2bfd0-114">Rimuove un'impostazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-114">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="2bfd0-115">[**\<clear>**](clear-element-for-custom-2.md)per <xref:System.Configuration.NameValueSectionHandler> e<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="2bfd0-115">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="2bfd0-116">Cancella tutte le impostazioni definite in precedenza in una sezione.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-116">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2bfd0-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="2bfd0-117">Remarks</span></span>

<span data-ttu-id="2bfd0-118">L' **\<sectionName>** elemento è un elemento personalizzato definito da un **\<section>** tag nell' **\<configSections>** elemento.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-118">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="2bfd0-119">La tabella seguente illustra il tipo di oggetto restituito dal metodo ConfigurationSettings. GetConfig per ogni gestore della sezione di configurazione:</span><span class="sxs-lookup"><span data-stu-id="2bfd0-119">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="2bfd0-120">Gestore della sezione di configurazione</span><span class="sxs-lookup"><span data-stu-id="2bfd0-120">Configuration section handler</span></span>                        | <span data-ttu-id="2bfd0-121">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="2bfd0-121">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="2bfd0-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="2bfd0-122">Example</span></span>

<span data-ttu-id="2bfd0-123">Nell'esempio seguente viene illustrato come dichiarare sezioni che utilizzano le <xref:System.Configuration.DictionarySectionHandler> <xref:System.Configuration.NameValueSectionHandler> classi e.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-123">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="2bfd0-124">Il primo elemento personalizzato è **\<dictionarySample>** , che contiene le impostazioni lette dalla <xref:System.Configuration.DictionarySectionHandler> classe nell' `System.dll` assembly.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-124">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="2bfd0-125">Il secondo elemento personalizzato è **\<mySection>** , che contiene le impostazioni lette dalla <xref:System.Configuration.NameValueSectionHandler> classe nell' `System.dll` assembly.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-125">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="2bfd0-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="2bfd0-126">Configuration file</span></span>

<span data-ttu-id="2bfd0-127">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2bfd0-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2bfd0-128">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2bfd0-128">See also</span></span>

- [<span data-ttu-id="2bfd0-129">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2bfd0-129">Configuration file schema for the .NET Framework</span></span>](index.md)
