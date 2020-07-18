---
title: Elemento <configSections> per <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 1e4bb7a7cfb0b140ca6d13c162708c3c30bd496d
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441687"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="1ad46-102">Elemento \<configSections> per \<configuration></span><span class="sxs-lookup"><span data-stu-id="1ad46-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="1ad46-103">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1ad46-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="1ad46-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="1ad46-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="1ad46-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="1ad46-105">Attributes</span></span>

<span data-ttu-id="1ad46-106">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1ad46-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="1ad46-107">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="1ad46-107">Parent element</span></span>

|     | <span data-ttu-id="1ad46-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ad46-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="1ad46-109">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ad46-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="1ad46-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1ad46-110">Child elements</span></span>

|     | <span data-ttu-id="1ad46-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ad46-111">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="1ad46-112">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1ad46-112">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="1ad46-113">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="1ad46-113">Defines a namespace for configuration sections.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1ad46-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="1ad46-114">Remarks</span></span>

<span data-ttu-id="1ad46-115">Se questo elemento si trova in un file di configurazione, deve essere il primo elemento figlio dell' **\<configuration>** elemento.</span><span class="sxs-lookup"><span data-stu-id="1ad46-115">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="1ad46-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ad46-116">Example</span></span>

<span data-ttu-id="1ad46-117">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per la sezione:</span><span class="sxs-lookup"><span data-stu-id="1ad46-117">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="1ad46-118">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="1ad46-118">Configuration file</span></span>

<span data-ttu-id="1ad46-119">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1ad46-119">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ad46-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ad46-120">See also</span></span>

- [<span data-ttu-id="1ad46-121">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1ad46-121">Configuration file schema for the .NET Framework</span></span>](index.md)
