---
title: '&lt;configSections&gt; elemento per &lt;configurazione&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 33406a67389cdf857fa5030e20d8a4dec7662741
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752078"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="18945-102">\<configSections > elemento per \<configurazione ></span><span class="sxs-lookup"><span data-stu-id="18945-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="18945-103">Contiene le dichiarazioni dello spazio dei nomi e di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="18945-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="18945-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="18945-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="18945-105">&nbsp;&nbsp;**\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="18945-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="18945-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="18945-106">Attributes</span></span>

<span data-ttu-id="18945-107">Nessuno</span><span class="sxs-lookup"><span data-stu-id="18945-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="18945-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="18945-108">Parent element</span></span>

|     | <span data-ttu-id="18945-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18945-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="18945-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="18945-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="18945-111">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="18945-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="18945-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="18945-112">Child elements</span></span>

|     | <span data-ttu-id="18945-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18945-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="18945-114">**\<sezione >**</span><span class="sxs-lookup"><span data-stu-id="18945-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="18945-115">Contiene una dichiarazione di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="18945-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="18945-116">**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="18945-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="18945-117">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="18945-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="18945-118">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="18945-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="18945-119">Rimuove una sezione predefinita o il gruppo di sezione.</span><span class="sxs-lookup"><span data-stu-id="18945-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="18945-120">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="18945-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="18945-121">Cancella tutte le sezioni definite in precedenza e i gruppi di sezioni.</span><span class="sxs-lookup"><span data-stu-id="18945-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="18945-122">Note</span><span class="sxs-lookup"><span data-stu-id="18945-122">Remarks</span></span>

<span data-ttu-id="18945-123">Se questo elemento è incluso un file di configurazione, deve essere il primo elemento figlio del  **\<configurazione >** elemento.</span><span class="sxs-lookup"><span data-stu-id="18945-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="18945-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="18945-124">Example</span></span>

<span data-ttu-id="18945-125">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e impostazioni per la sezione:</span><span class="sxs-lookup"><span data-stu-id="18945-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="18945-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="18945-126">Configuration file</span></span>

<span data-ttu-id="18945-127">Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18945-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="18945-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18945-128">See also</span></span>

[<span data-ttu-id="18945-129">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="18945-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
