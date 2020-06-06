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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155349"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="d495b-102">Elemento \<configSections> per \<configuration></span><span class="sxs-lookup"><span data-stu-id="d495b-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="d495b-103">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d495b-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="d495b-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="d495b-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="d495b-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="d495b-105">Attributes</span></span>

<span data-ttu-id="d495b-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="d495b-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="d495b-107">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="d495b-107">Parent element</span></span>

|     | <span data-ttu-id="d495b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d495b-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="d495b-109">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d495b-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d495b-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d495b-110">Child elements</span></span>

|     | <span data-ttu-id="d495b-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d495b-111">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="d495b-112">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d495b-112">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="d495b-113">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d495b-113">Defines a namespace for configuration sections.</span></span> |
| [**\<remove>**](remove-element-for-configsections.md) | <span data-ttu-id="d495b-114">Rimuove una sezione o un gruppo di sezioni predefinito.</span><span class="sxs-lookup"><span data-stu-id="d495b-114">Removes a predefined section or section group.</span></span> |
| [**\<clear>**](clear-element-for-configsections.md) | <span data-ttu-id="d495b-115">Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d495b-115">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d495b-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="d495b-116">Remarks</span></span>

<span data-ttu-id="d495b-117">Se questo elemento si trova in un file di configurazione, deve essere il primo elemento figlio dell' **\<configuration>** elemento.</span><span class="sxs-lookup"><span data-stu-id="d495b-117">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="d495b-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d495b-118">Example</span></span>

<span data-ttu-id="d495b-119">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per la sezione:</span><span class="sxs-lookup"><span data-stu-id="d495b-119">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="d495b-120">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d495b-120">Configuration file</span></span>

<span data-ttu-id="d495b-121">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d495b-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d495b-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d495b-122">See also</span></span>

- [<span data-ttu-id="d495b-123">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d495b-123">Configuration file schema for the .NET Framework</span></span>](index.md)
