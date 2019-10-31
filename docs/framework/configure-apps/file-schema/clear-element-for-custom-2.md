---
title: elemento <clear> per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e27bb7e21baf2eb4990d0107db4aae1b5f9a7d1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119066"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="d7544-102">\<elemento clear > per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="d7544-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="d7544-103">Cancella tutte le impostazioni definite in precedenza in una sezione.</span><span class="sxs-lookup"><span data-stu-id="d7544-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="d7544-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d7544-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="d7544-105">&nbsp;&nbsp;[ **\<sectionname >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="d7544-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="d7544-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<cancella >**</span><span class="sxs-lookup"><span data-stu-id="d7544-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d7544-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7544-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="d7544-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="d7544-108">Attributes</span></span>

<span data-ttu-id="d7544-109">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d7544-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="d7544-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="d7544-110">Parent element</span></span>

|     | <span data-ttu-id="d7544-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7544-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="d7544-112"> **\<sectionname >** Elemento</span><span class="sxs-lookup"><span data-stu-id="d7544-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="d7544-113">Definisce le impostazioni per le sezioni di configurazione personalizzate che usano le classi <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="d7544-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d7544-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d7544-114">Child elements</span></span>

<span data-ttu-id="d7544-115">Nessuno</span><span class="sxs-lookup"><span data-stu-id="d7544-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="d7544-116">Note</span><span class="sxs-lookup"><span data-stu-id="d7544-116">Remarks</span></span>

<span data-ttu-id="d7544-117">È possibile utilizzare l'elemento **\<clear >** per rimuovere tutte le impostazioni dall'applicazione definite a un livello superiore nella gerarchia dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d7544-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="d7544-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7544-118">Example</span></span>

<span data-ttu-id="d7544-119">Questo esempio definisce un file di configurazione del computer e un file di configurazione dell'applicazione e Mostra come usare l'elemento **\<clear >** in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="d7544-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="d7544-120">Il seguente codice del file di configurazione del computer dichiara la sezione **\<sezione >** :</span><span class="sxs-lookup"><span data-stu-id="d7544-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="d7544-121">Il codice del file di configurazione dell'applicazione seguente consente di rimuovere tutte le impostazioni da **\<> sezione**.</span><span class="sxs-lookup"><span data-stu-id="d7544-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="d7544-122">L'applicazione non è in grado di recuperare le impostazioni dichiarate nella sezione **\<sezione >** del file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="d7544-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="d7544-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d7544-123">Configuration file</span></span>

<span data-ttu-id="d7544-124">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d7544-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7544-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7544-125">See also</span></span>

- [<span data-ttu-id="d7544-126">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d7544-126">Configuration file schema for the .NET Framework</span></span>](index.md)
