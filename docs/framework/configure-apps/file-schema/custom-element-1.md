---
title: Elemento personalizzato per SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 1d0431085a04d3fb817dfe0883779acc4d693084
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214795"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="a850e-102">Elemento personalizzato per SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="a850e-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="a850e-103">Definisce le impostazioni in una sezione di configurazione personalizzata definita da una sezione \<> elemento e utilizza la classe <xref:System.Configuration.SingleTagSectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="a850e-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="a850e-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="a850e-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="a850e-105">&nbsp;&nbsp; *\<sectionname >*</span><span class="sxs-lookup"><span data-stu-id="a850e-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="a850e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a850e-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="a850e-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="a850e-107">Attributes</span></span>

<span data-ttu-id="a850e-108">Attributi e valori di attributo sono definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a850e-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="a850e-109">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="a850e-109">Parent element</span></span>

|     | <span data-ttu-id="a850e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a850e-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a850e-111"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="a850e-111">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="a850e-112">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a850e-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a850e-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a850e-113">Child elements</span></span>

<span data-ttu-id="a850e-114">nessuno</span><span class="sxs-lookup"><span data-stu-id="a850e-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="a850e-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a850e-115">Remarks</span></span>

<span data-ttu-id="a850e-116">L'elemento **\<sectionname >** è un elemento personalizzato definito da una [**sezione di\<>** ](section-element.md) tag nell'elemento\<[**configSections >** ](configsections-element-for-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="a850e-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="a850e-117">Quando si chiama <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>, il sistema di configurazione restituisce un oggetto <xref:System.Collections.IDictionary>.</span><span class="sxs-lookup"><span data-stu-id="a850e-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="a850e-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="a850e-118">Example</span></span>

<span data-ttu-id="a850e-119">Nell'esempio seguente viene dichiarato un elemento personalizzato denominato **\<sampleSection >** che contiene le impostazioni lette dalla classe <xref:System.Configuration.SingleTagSectionHandler>:</span><span class="sxs-lookup"><span data-stu-id="a850e-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="a850e-120">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="a850e-120">Configuration file</span></span>

<span data-ttu-id="a850e-121">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a850e-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a850e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a850e-122">See also</span></span>

- [<span data-ttu-id="a850e-123">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a850e-123">Configuration file schema for the .NET Framework</span></span>](index.md)
