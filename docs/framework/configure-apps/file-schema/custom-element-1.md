---
title: Elemento personalizzato per SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: a40f35838655f6021af0b2e966335803ec8c16b4
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635391"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="75b1d-102">Elemento personalizzato per SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="75b1d-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="75b1d-103">Definisce le impostazioni in una sezione \<di configurazione personalizzata <xref:System.Configuration.SingleTagSectionHandler> definita da una sezione> elemento e utilizza la classe .</span><span class="sxs-lookup"><span data-stu-id="75b1d-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="75b1d-104">sezione &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) \* \<configurazioneNome>\*</span><span class="sxs-lookup"><span data-stu-id="75b1d-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="75b1d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75b1d-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="75b1d-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="75b1d-106">Attributes</span></span>

<span data-ttu-id="75b1d-107">Gli attributi e i valori degli attributi sono definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="75b1d-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="75b1d-108">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="75b1d-108">Parent element</span></span>

|     | <span data-ttu-id="75b1d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75b1d-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="75b1d-110">**\<>di configurazione**</span><span class="sxs-lookup"><span data-stu-id="75b1d-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="75b1d-111">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75b1d-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="75b1d-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="75b1d-112">Child elements</span></span>

<span data-ttu-id="75b1d-113">nessuno</span><span class="sxs-lookup"><span data-stu-id="75b1d-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="75b1d-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="75b1d-114">Remarks</span></span>

<span data-ttu-id="75b1d-115">L'elemento \*\* \<>sectionName\*\* è un [\*\* \<\*\*](section-element.md) elemento personalizzato definito da una sezione>tag nell'elemento [\*\* \<>configSections.\*\*](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="75b1d-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="75b1d-116">Il sistema di <xref:System.Collections.IDictionary> configurazione restituisce un oggetto quando si chiama <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="75b1d-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="75b1d-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="75b1d-117">Example</span></span>

<span data-ttu-id="75b1d-118">L'esempio seguente dichiara un elemento personalizzato denominato \*\* \<sampleSection>\*\* che contiene le impostazioni lette dalla classe:The following example declares a custom element called sampleSection>that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span><span class="sxs-lookup"><span data-stu-id="75b1d-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="75b1d-119">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="75b1d-119">Configuration file</span></span>

<span data-ttu-id="75b1d-120">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75b1d-120">This element can be used in the application configuration file, the machine configuration file (*Machine.config*), and *Web.config* files that aren't at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="75b1d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75b1d-121">See also</span></span>

- [<span data-ttu-id="75b1d-122">Schema del file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="75b1d-122">Configuration file schema for the .NET Framework</span></span>](index.md)
