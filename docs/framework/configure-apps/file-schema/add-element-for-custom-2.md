---
title: '&lt;aggiungere&gt; elemento per NameValueSectionHandler e DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 502f86e49d68e456d8e64e00e7632aa603cafbe9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523909"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="984c6-102">\<Aggiungi > elemento per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="984c6-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="984c6-103">Aggiunge impostazioni personalizzate dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="984c6-103">Adds custom application settings.</span></span> <span data-ttu-id="984c6-104">Ciascuna  **\<Aggiungi >** tag contiene una coppia chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="984c6-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="984c6-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="984c6-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="984c6-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="984c6-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="984c6-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span><span class="sxs-lookup"><span data-stu-id="984c6-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="984c6-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="984c6-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="984c6-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="984c6-109">Attributes</span></span>

| <span data-ttu-id="984c6-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="984c6-110">Attribute</span></span> | <span data-ttu-id="984c6-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="984c6-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="984c6-112">**key**</span><span class="sxs-lookup"><span data-stu-id="984c6-112">**key**</span></span>   | <span data-ttu-id="984c6-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="984c6-113">Required attribute.</span></span><br><br><span data-ttu-id="984c6-114">Specifica il nome dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="984c6-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="984c6-115">**value**</span><span class="sxs-lookup"><span data-stu-id="984c6-115">**value**</span></span> | <span data-ttu-id="984c6-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="984c6-116">Required attribute.</span></span><br><br><span data-ttu-id="984c6-117">Specifica il valore dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="984c6-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="984c6-118">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="984c6-118">Parent element</span></span>

| <span data-ttu-id="984c6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="984c6-119">Element</span></span> | <span data-ttu-id="984c6-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="984c6-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="984c6-121">**\<sectionName >** elemento</span><span class="sxs-lookup"><span data-stu-id="984c6-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="984c6-122">Definisce le impostazioni per le sezioni di configurazione personalizzati che usano il <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> classi.</span><span class="sxs-lookup"><span data-stu-id="984c6-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="984c6-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="984c6-123">Child elements</span></span>

<span data-ttu-id="984c6-124">nessuno</span><span class="sxs-lookup"><span data-stu-id="984c6-124">None</span></span>

## <a name="example"></a><span data-ttu-id="984c6-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="984c6-125">Example</span></span>

<span data-ttu-id="984c6-126">Nell'esempio seguente viene illustrato come definire una sezione di configurazione personalizzato e usare la  **\<Aggiungi >** elemento da inserire nella sezione impostazioni:</span><span class="sxs-lookup"><span data-stu-id="984c6-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="984c6-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="984c6-127">Configuration file</span></span>

<span data-ttu-id="984c6-128">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="984c6-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="984c6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="984c6-129">See also</span></span>

- [<span data-ttu-id="984c6-130">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="984c6-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
