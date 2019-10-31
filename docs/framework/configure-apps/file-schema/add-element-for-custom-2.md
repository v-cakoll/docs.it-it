---
title: elemento <add> per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e7d68530ae1f0666fc4940ffe7605c3bf8dfe3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119606"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="575ce-102">\<aggiungere > elemento per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="575ce-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="575ce-103">Aggiunge le impostazioni dell'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="575ce-103">Adds custom application settings.</span></span> <span data-ttu-id="575ce-104">Ogni **\<Aggiungi tag >** contiene una coppia chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="575ce-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="575ce-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="575ce-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="575ce-106">&nbsp;&nbsp;[ **\<sectionname >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="575ce-106">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="575ce-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<aggiungi >**</span><span class="sxs-lookup"><span data-stu-id="575ce-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="575ce-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="575ce-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="575ce-109">Attributi</span><span class="sxs-lookup"><span data-stu-id="575ce-109">Attributes</span></span>

| <span data-ttu-id="575ce-110">Attributo</span><span class="sxs-lookup"><span data-stu-id="575ce-110">Attribute</span></span> | <span data-ttu-id="575ce-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575ce-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="575ce-112">**key**</span><span class="sxs-lookup"><span data-stu-id="575ce-112">**key**</span></span>   | <span data-ttu-id="575ce-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="575ce-113">Required attribute.</span></span><br><br><span data-ttu-id="575ce-114">Specifica il nome dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="575ce-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="575ce-115">**valore**</span><span class="sxs-lookup"><span data-stu-id="575ce-115">**value**</span></span> | <span data-ttu-id="575ce-116">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="575ce-116">Required attribute.</span></span><br><br><span data-ttu-id="575ce-117">Specifica il valore dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="575ce-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="575ce-118">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="575ce-118">Parent element</span></span>

| <span data-ttu-id="575ce-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="575ce-119">Element</span></span> | <span data-ttu-id="575ce-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="575ce-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="575ce-121"> **\<sectionname >** Elemento</span><span class="sxs-lookup"><span data-stu-id="575ce-121">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="575ce-122">Definisce le impostazioni per le sezioni di configurazione personalizzate che usano le classi <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="575ce-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="575ce-123">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="575ce-123">Child elements</span></span>

<span data-ttu-id="575ce-124">Nessuno</span><span class="sxs-lookup"><span data-stu-id="575ce-124">None</span></span>

## <a name="example"></a><span data-ttu-id="575ce-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="575ce-125">Example</span></span>

<span data-ttu-id="575ce-126">Nell'esempio seguente viene illustrato come definire una sezione di configurazione personalizzata e utilizzare l'elemento **\<aggiungi >** per inserire le impostazioni nella sezione:</span><span class="sxs-lookup"><span data-stu-id="575ce-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="575ce-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="575ce-127">Configuration file</span></span>

<span data-ttu-id="575ce-128">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="575ce-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="575ce-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="575ce-129">See also</span></span>

- [<span data-ttu-id="575ce-130">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="575ce-130">Configuration file schema for the .NET Framework</span></span>](index.md)
