---
title: Elemento <configSections> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6024144b6f12df22369366f04c3cbad02c5011d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119024"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="2f27e-102">\<elemento > configSections per \<Configuration ></span><span class="sxs-lookup"><span data-stu-id="2f27e-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="2f27e-103">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2f27e-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="2f27e-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2f27e-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="2f27e-105">&nbsp;&nbsp; **\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="2f27e-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="2f27e-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="2f27e-106">Attributes</span></span>

<span data-ttu-id="2f27e-107">None</span><span class="sxs-lookup"><span data-stu-id="2f27e-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="2f27e-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="2f27e-108">Parent element</span></span>

|     | <span data-ttu-id="2f27e-109">description</span><span class="sxs-lookup"><span data-stu-id="2f27e-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2f27e-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2f27e-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="2f27e-111">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f27e-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2f27e-112">Elemento figlio</span><span class="sxs-lookup"><span data-stu-id="2f27e-112">Child elements</span></span>

|     | <span data-ttu-id="2f27e-113">description</span><span class="sxs-lookup"><span data-stu-id="2f27e-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2f27e-114"> **\<sezione >** </span><span class="sxs-lookup"><span data-stu-id="2f27e-114">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="2f27e-115">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2f27e-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="2f27e-116"> **\<sectionGroup>** </span><span class="sxs-lookup"><span data-stu-id="2f27e-116">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="2f27e-117">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2f27e-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="2f27e-118"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="2f27e-118">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="2f27e-119">Rimuove una sezione o un gruppo di sezioni predefinito.</span><span class="sxs-lookup"><span data-stu-id="2f27e-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="2f27e-120"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="2f27e-120">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="2f27e-121">Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2f27e-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2f27e-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2f27e-122">Remarks</span></span>

<span data-ttu-id="2f27e-123">Se questo elemento si trova in un file di configurazione, deve essere il primo elemento figlio dell'elemento **\<configuration >** .</span><span class="sxs-lookup"><span data-stu-id="2f27e-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="2f27e-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="2f27e-124">Example</span></span>

<span data-ttu-id="2f27e-125">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per la sezione:</span><span class="sxs-lookup"><span data-stu-id="2f27e-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="2f27e-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="2f27e-126">Configuration file</span></span>

<span data-ttu-id="2f27e-127">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2f27e-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f27e-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f27e-128">See also</span></span>

- [<span data-ttu-id="2f27e-129">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2f27e-129">Configuration file schema for the .NET Framework</span></span>](index.md)
