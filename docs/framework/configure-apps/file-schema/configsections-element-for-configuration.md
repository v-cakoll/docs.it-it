---
title: '&lt;configSections&gt; (elemento) per &lt;configurazione&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
ms.openlocfilehash: f46c84a1674a3e9352d0a4ccda23d44e650a70ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629488"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="7a24c-102">\<configSections > (elemento) per \<configuration ></span><span class="sxs-lookup"><span data-stu-id="7a24c-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="7a24c-103">Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a24c-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="7a24c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7a24c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7a24c-105">&nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="7a24c-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="7a24c-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="7a24c-106">Attributes</span></span>

<span data-ttu-id="7a24c-107">nessuno</span><span class="sxs-lookup"><span data-stu-id="7a24c-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="7a24c-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="7a24c-108">Parent element</span></span>

|     | <span data-ttu-id="7a24c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a24c-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7a24c-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="7a24c-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="7a24c-111">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a24c-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7a24c-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7a24c-112">Child elements</span></span>

|     | <span data-ttu-id="7a24c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a24c-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7a24c-114">**\<sezione >**</span><span class="sxs-lookup"><span data-stu-id="7a24c-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="7a24c-115">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a24c-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="7a24c-116">**\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="7a24c-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="7a24c-117">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a24c-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="7a24c-118">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="7a24c-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="7a24c-119">Rimuove una sezione predefiniti o un gruppo di sezioni.</span><span class="sxs-lookup"><span data-stu-id="7a24c-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="7a24c-120">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="7a24c-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="7a24c-121">Cancella tutte le sezioni definite in precedenza e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="7a24c-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7a24c-122">Note</span><span class="sxs-lookup"><span data-stu-id="7a24c-122">Remarks</span></span>

<span data-ttu-id="7a24c-123">Se questo elemento è in un file di configurazione, deve essere il primo elemento figlio del  **\<configuration >** elemento.</span><span class="sxs-lookup"><span data-stu-id="7a24c-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="7a24c-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a24c-124">Example</span></span>

<span data-ttu-id="7a24c-125">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per tale sezione:</span><span class="sxs-lookup"><span data-stu-id="7a24c-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="7a24c-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="7a24c-126">Configuration file</span></span>

<span data-ttu-id="7a24c-127">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7a24c-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a24c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a24c-128">See also</span></span>

- [<span data-ttu-id="7a24c-129">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7a24c-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
