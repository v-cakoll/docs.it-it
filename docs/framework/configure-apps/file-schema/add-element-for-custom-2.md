---
title: <add>elemento per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 57722f3518fad12cb8e6e35d68f40bb8465bdd86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215443"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="26b68-102">\<add>elemento per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="26b68-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="26b68-103">Aggiunge le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="26b68-103">Adds custom application settings.</span></span> <span data-ttu-id="26b68-104">Ogni **\<add>** tag contiene una coppia chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="26b68-104">Each **\<add>** tag contains a key/value pair.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="26b68-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26b68-105">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="26b68-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="26b68-106">Attributes</span></span>

| <span data-ttu-id="26b68-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="26b68-107">Attribute</span></span> | <span data-ttu-id="26b68-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26b68-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="26b68-109">**key**</span><span class="sxs-lookup"><span data-stu-id="26b68-109">**key**</span></span>   | <span data-ttu-id="26b68-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="26b68-110">Required attribute.</span></span><br><br><span data-ttu-id="26b68-111">Specifica il nome dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="26b68-111">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="26b68-112">**value**</span><span class="sxs-lookup"><span data-stu-id="26b68-112">**value**</span></span> | <span data-ttu-id="26b68-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="26b68-113">Required attribute.</span></span><br><br><span data-ttu-id="26b68-114">Specifica il valore dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="26b68-114">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="26b68-115">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="26b68-115">Parent element</span></span>

| <span data-ttu-id="26b68-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="26b68-116">Element</span></span> | <span data-ttu-id="26b68-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="26b68-117">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="26b68-118">**\<sectionName>** Elemento</span><span class="sxs-lookup"><span data-stu-id="26b68-118">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="26b68-119">Definisce le impostazioni per le sezioni di configurazione personalizzate che usano le <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> classi e.</span><span class="sxs-lookup"><span data-stu-id="26b68-119">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="26b68-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="26b68-120">Child elements</span></span>

<span data-ttu-id="26b68-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="26b68-121">None</span></span>

## <a name="example"></a><span data-ttu-id="26b68-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="26b68-122">Example</span></span>

<span data-ttu-id="26b68-123">Nell'esempio seguente viene illustrato come definire una sezione di configurazione personalizzata e utilizzare l' **\<add>** elemento per inserire le impostazioni nella sezione:</span><span class="sxs-lookup"><span data-stu-id="26b68-123">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="26b68-124">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="26b68-124">Configuration file</span></span>

<span data-ttu-id="26b68-125">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="26b68-125">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="26b68-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="26b68-126">See also</span></span>

- [<span data-ttu-id="26b68-127">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="26b68-127">Configuration file schema for the .NET Framework</span></span>](index.md)
