---
title: '&lt;Cancella&gt; elemento per NameValueSectionHandler e DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 55925ee5e9c5a17f14bd199125dbaacbadb9d928
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720941"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="4ac69-102">\<Cancella > elemento per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="4ac69-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="4ac69-103">Cancella tutte le impostazioni definite in precedenza in una sezione.</span><span class="sxs-lookup"><span data-stu-id="4ac69-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="4ac69-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="4ac69-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="4ac69-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="4ac69-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="4ac69-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="4ac69-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4ac69-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ac69-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="4ac69-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ac69-108">Attributes</span></span>

<span data-ttu-id="4ac69-109">nessuno</span><span class="sxs-lookup"><span data-stu-id="4ac69-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="4ac69-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="4ac69-110">Parent element</span></span>

|     | <span data-ttu-id="4ac69-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ac69-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="4ac69-112">**\<sectionName >** elemento</span><span class="sxs-lookup"><span data-stu-id="4ac69-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="4ac69-113">Definisce le impostazioni per le sezioni di configurazione personalizzati che usano il <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler> classi.</span><span class="sxs-lookup"><span data-stu-id="4ac69-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4ac69-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ac69-114">Child elements</span></span>

<span data-ttu-id="4ac69-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="4ac69-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="4ac69-116">Note</span><span class="sxs-lookup"><span data-stu-id="4ac69-116">Remarks</span></span>

<span data-ttu-id="4ac69-117">È possibile usare la  **\<clear >** elemento da cui rimuovere tutte le impostazioni dall'applicazione che sono stati definiti a un livello superiore nella gerarchia di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ac69-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="4ac69-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ac69-118">Example</span></span>

<span data-ttu-id="4ac69-119">In questo esempio definisce un file di configurazione di computer e un file di configurazione dell'applicazione e viene illustrato come utilizzare il  **\<clear >** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza di file di configurazione macchina.</span><span class="sxs-lookup"><span data-stu-id="4ac69-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="4ac69-120">Il codice di file di configurazione macchina seguente dichiara la sezione  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="4ac69-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="4ac69-121">Il codice di file di configurazione dell'applicazione seguente rimuove tutte le impostazioni nelle  **\<mySection >**.</span><span class="sxs-lookup"><span data-stu-id="4ac69-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="4ac69-122">L'applicazione non è possibile recuperare le impostazioni che sono state dichiarate nel nel  **\<mySection >** sezione del file di configurazione della macchina.</span><span class="sxs-lookup"><span data-stu-id="4ac69-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="4ac69-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="4ac69-123">Configuration file</span></span>

<span data-ttu-id="4ac69-124">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ac69-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ac69-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ac69-125">See also</span></span>

- [<span data-ttu-id="4ac69-126">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4ac69-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
