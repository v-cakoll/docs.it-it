---
title: Elemento personalizzato per SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 04360a796b18cf1e414f1f84bff247a1e9d8ef9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155154"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="c8630-102">Elemento personalizzato per SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="c8630-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="c8630-103">Definisce le impostazioni in una sezione \<di configurazione personalizzata <xref:System.Configuration.SingleTagSectionHandler> definita da una sezione> elemento e utilizza la classe .</span><span class="sxs-lookup"><span data-stu-id="c8630-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="c8630-104">sezione &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) \* \<configurazioneNome>\*</span><span class="sxs-lookup"><span data-stu-id="c8630-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="c8630-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8630-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="c8630-106">Attributes</span><span class="sxs-lookup"><span data-stu-id="c8630-106">Attributes</span></span>

<span data-ttu-id="c8630-107">Gli attributi e i valori degli attributi sono definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c8630-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="c8630-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="c8630-108">Parent element</span></span>

|     | <span data-ttu-id="c8630-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8630-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c8630-110">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="c8630-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="c8630-111">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8630-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c8630-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c8630-112">Child elements</span></span>

<span data-ttu-id="c8630-113">nessuno</span><span class="sxs-lookup"><span data-stu-id="c8630-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="c8630-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c8630-114">Remarks</span></span>

<span data-ttu-id="c8630-115">L'elemento \*\* \<>sectionName\*\* è un [\*\* \<\*\*](section-element.md) elemento personalizzato definito da una sezione>tag nell'elemento [\*\* \<>configSections.\*\*](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="c8630-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="c8630-116">Il sistema di <xref:System.Collections.IDictionary> configurazione restituisce un oggetto quando si chiama <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c8630-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="c8630-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8630-117">Example</span></span>

<span data-ttu-id="c8630-118">L'esempio seguente dichiara un elemento personalizzato denominato \*\* \<sampleSection>\*\* che contiene le impostazioni lette dalla classe:The following example declares a custom element called sampleSection>that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span><span class="sxs-lookup"><span data-stu-id="c8630-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="c8630-119">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c8630-119">Configuration file</span></span>

<span data-ttu-id="c8630-120">Questo elemento può essere utilizzato nei file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c8630-120">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8630-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8630-121">See also</span></span>

- [<span data-ttu-id="c8630-122">Schema del file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c8630-122">Configuration file schema for the .NET Framework</span></span>](index.md)
