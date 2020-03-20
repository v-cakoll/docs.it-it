---
title: Elemento <configSections> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155349"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="8c2fa-102">\<elemento di> \<configSections per la> di configurazione</span><span class="sxs-lookup"><span data-stu-id="8c2fa-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="8c2fa-103">Contiene le dichiarazioni della sezione di configurazione e dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8c2fa-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="8c2fa-104">[\*\* \<>\*\*](configuration-element.md) &nbsp; &nbsp;configurazione configSections>\*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="8c2fa-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="8c2fa-105">Attributes</span><span class="sxs-lookup"><span data-stu-id="8c2fa-105">Attributes</span></span>

<span data-ttu-id="8c2fa-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="8c2fa-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="8c2fa-107">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="8c2fa-107">Parent element</span></span>

|     | <span data-ttu-id="8c2fa-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c2fa-108">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8c2fa-109">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="8c2fa-109">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="8c2fa-110">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8c2fa-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8c2fa-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8c2fa-111">Child elements</span></span>

|     | <span data-ttu-id="8c2fa-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c2fa-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8c2fa-113">**\<sezione>**</span><span class="sxs-lookup"><span data-stu-id="8c2fa-113">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="8c2fa-114">Contiene una dichiarazione di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8c2fa-114">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="8c2fa-115">**\<>gruppo section**</span><span class="sxs-lookup"><span data-stu-id="8c2fa-115">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="8c2fa-116">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8c2fa-116">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="8c2fa-117">**\<rimuovere>**</span><span class="sxs-lookup"><span data-stu-id="8c2fa-117">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="8c2fa-118">Rimuove una sezione o un gruppo di sezioni predefinito.</span><span class="sxs-lookup"><span data-stu-id="8c2fa-118">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="8c2fa-119">**\<>chiari**</span><span class="sxs-lookup"><span data-stu-id="8c2fa-119">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="8c2fa-120">Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8c2fa-120">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8c2fa-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8c2fa-121">Remarks</span></span>

<span data-ttu-id="8c2fa-122">Se questo elemento si trova in un file di configurazione, deve essere il primo elemento figlio dell'elemento \*\* \<>configurazione.\*\*</span><span class="sxs-lookup"><span data-stu-id="8c2fa-122">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="8c2fa-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c2fa-123">Example</span></span>

<span data-ttu-id="8c2fa-124">L'esempio seguente mostra come definire una sezione di configurazione e definire le impostazioni per tale sezione:The following example shows how to define a configuration section and define settings for that section:</span><span class="sxs-lookup"><span data-stu-id="8c2fa-124">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="8c2fa-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="8c2fa-125">Configuration file</span></span>

<span data-ttu-id="8c2fa-126">Questo elemento può essere utilizzato nei file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8c2fa-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c2fa-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c2fa-127">See also</span></span>

- [<span data-ttu-id="8c2fa-128">Schema del file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8c2fa-128">Configuration file schema for the .NET Framework</span></span>](index.md)
