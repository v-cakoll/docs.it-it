---
title: Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords: custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2154e2a178050e5bafa7d19f37a766141d0a5838
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="62d47-102">Elemento personalizzato per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="62d47-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="62d47-103">Definisce le impostazioni per le sezioni di configurazione personalizzate che utilizzano il <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> classi.</span><span class="sxs-lookup"><span data-stu-id="62d47-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="62d47-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="62d47-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="62d47-105">&nbsp;&nbsp;**\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="62d47-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="62d47-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="62d47-106">Attributes</span></span>

<span data-ttu-id="62d47-107">nessuno</span><span class="sxs-lookup"><span data-stu-id="62d47-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="62d47-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="62d47-108">Parent element</span></span>

|     | <span data-ttu-id="62d47-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62d47-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="62d47-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="62d47-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="62d47-111">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="62d47-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="62d47-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="62d47-112">Child elements</span></span>

|     | <span data-ttu-id="62d47-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="62d47-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="62d47-114">[**\<aggiungere >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) per <xref:System.Configuration.NameValueSectionHandler> e<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="62d47-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="62d47-115">Aggiunge le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="62d47-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="62d47-116">[**\<rimuovere >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) per <xref:System.Configuration.NameValueSectionHandler> e<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="62d47-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> |    <span data-ttu-id="62d47-117">Rimuove un'impostazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="62d47-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="62d47-118">[**\<Deselezionare >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) per <xref:System.Configuration.NameValueSectionHandler> e<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="62d47-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="62d47-119">Cancella tutte le impostazioni definite in precedenza in una sezione.</span><span class="sxs-lookup"><span data-stu-id="62d47-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="62d47-120">Note</span><span class="sxs-lookup"><span data-stu-id="62d47-120">Remarks</span></span>

<span data-ttu-id="62d47-121">Il  **\<sectionName >** è un elemento personalizzato definito da un  **\<sezione >** tag il  **\<configSections >**elemento.</span><span class="sxs-lookup"><span data-stu-id="62d47-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="62d47-122">Nella tabella seguente viene illustrato che il tipo di oggetto, il metodo GetConfig restituisce per ogni gestore della sezione di configurazione:</span><span class="sxs-lookup"><span data-stu-id="62d47-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="62d47-123">Gestore della sezione di configurazione</span><span class="sxs-lookup"><span data-stu-id="62d47-123">Configuration section handler</span></span>                        | <span data-ttu-id="62d47-124">Tipo restituito</span><span class="sxs-lookup"><span data-stu-id="62d47-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="62d47-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="62d47-125">Example</span></span>

<span data-ttu-id="62d47-126">Nell'esempio seguente viene illustrato come dichiarare le sezioni che utilizzano il <xref:System.Configuration.DictionarySectionHandler> e <xref:System.Configuration.NameValueSectionHandler> classi.</span><span class="sxs-lookup"><span data-stu-id="62d47-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span> 

<span data-ttu-id="62d47-127">Il primo elemento personalizzato è  **\<dictionarySample >**, che contiene le impostazioni di lettura per il <xref:System.Configuration.DictionarySectionHandler> classe il `System.dll` assembly.</span><span class="sxs-lookup"><span data-stu-id="62d47-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="62d47-128">Il secondo elemento personalizzato è  **\<mySection >**, che contiene le impostazioni di lettura per il <xref:System.Configuration.NameValueSectionHandler> classe il `System.dll` assembly.</span><span class="sxs-lookup"><span data-stu-id="62d47-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="62d47-129">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="62d47-129">Configuration file</span></span>

<span data-ttu-id="62d47-130">Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62d47-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="62d47-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62d47-131">See also</span></span>

[<span data-ttu-id="62d47-132">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="62d47-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
