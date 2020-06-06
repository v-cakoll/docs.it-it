---
title: Elemento personalizzato per SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "80635391"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="68a49-102">Elemento personalizzato per SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="68a49-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="68a49-103">Definisce le impostazioni in una sezione di configurazione personalizzata definita da un \<section> elemento e utilizza la <xref:System.Configuration.SingleTagSectionHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="68a49-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="68a49-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="68a49-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="68a49-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68a49-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="68a49-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="68a49-106">Attributes</span></span>

<span data-ttu-id="68a49-107">Attributi e valori di attributo sono definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="68a49-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="68a49-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="68a49-108">Parent element</span></span>

|     | <span data-ttu-id="68a49-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68a49-109">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="68a49-110">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="68a49-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="68a49-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="68a49-111">Child elements</span></span>

<span data-ttu-id="68a49-112">nessuno</span><span class="sxs-lookup"><span data-stu-id="68a49-112">None</span></span>

## <a name="remarks"></a><span data-ttu-id="68a49-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="68a49-113">Remarks</span></span>

<span data-ttu-id="68a49-114">L' **\<sectionName>** elemento è un elemento personalizzato definito da un [**\<section>**](section-element.md) tag nell' [**\<configSections>**](configsections-element-for-configuration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="68a49-114">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="68a49-115">Il sistema di configurazione restituisce un <xref:System.Collections.IDictionary> oggetto quando si chiama <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="68a49-115">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="68a49-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="68a49-116">Example</span></span>

<span data-ttu-id="68a49-117">Nell'esempio seguente viene dichiarato un elemento personalizzato denominato **\<sampleSection>** che contiene le impostazioni lette dalla <xref:System.Configuration.SingleTagSectionHandler> classe:</span><span class="sxs-lookup"><span data-stu-id="68a49-117">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="68a49-118">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="68a49-118">Configuration file</span></span>

<span data-ttu-id="68a49-119">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="68a49-119">This element can be used in the application configuration file, the machine configuration file (*Machine.config*), and *Web.config* files that aren't at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="68a49-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="68a49-120">See also</span></span>

- [<span data-ttu-id="68a49-121">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="68a49-121">Configuration file schema for the .NET Framework</span></span>](index.md)
