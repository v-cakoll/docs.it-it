---
title: Elemento personalizzato per SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bfc2a916e37ac27d45746eb268912b3752f4d80f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705298"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="1566f-102">Elemento personalizzato per SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="1566f-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="1566f-103">Definisce le impostazioni in una sezione di configurazione personalizzati che è definita da un \<sezione > elemento e viene utilizzato il <xref:System.Configuration.SingleTagSectionHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="1566f-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="1566f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="1566f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="1566f-105">&nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="1566f-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="1566f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1566f-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="1566f-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="1566f-107">Attributes</span></span>

<span data-ttu-id="1566f-108">Gli attributi e valori di attributo sono definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1566f-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="1566f-109">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="1566f-109">Parent element</span></span>

|     | <span data-ttu-id="1566f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1566f-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1566f-111">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="1566f-111">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="1566f-112">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1566f-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="1566f-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1566f-113">Child elements</span></span>

<span data-ttu-id="1566f-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="1566f-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="1566f-115">Note</span><span class="sxs-lookup"><span data-stu-id="1566f-115">Remarks</span></span>

<span data-ttu-id="1566f-116">Il  **\<sectionName >** è un elemento personalizzato definito da una [  **\<sezione >** ](~/docs/framework/configure-apps/file-schema/section-element.md) contrassegnare nel [  **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1566f-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="1566f-117">Il sistema di configurazione restituisce un <xref:System.Collections.IDictionary> dell'oggetto quando si chiama <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1566f-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="1566f-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="1566f-118">Example</span></span>

<span data-ttu-id="1566f-119">L'esempio seguente dichiara un elemento personalizzato chiamato  **\<sampleSection >** che contiene le impostazioni lette dal <xref:System.Configuration.SingleTagSectionHandler> classe:</span><span class="sxs-lookup"><span data-stu-id="1566f-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="1566f-120">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1566f-120">Configuration file</span></span>

<span data-ttu-id="1566f-121">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1566f-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="1566f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1566f-122">See also</span></span>

- [<span data-ttu-id="1566f-123">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1566f-123">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
