---
title: <remove>elemento per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: cd338ff2d613be31ab1524f6baed6107f803a688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920943"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="3256b-102">\<rimuovere > elemento per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="3256b-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="3256b-103">Rimuove un'impostazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3256b-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="3256b-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="3256b-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="3256b-105">&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="3256b-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="3256b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="3256b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3256b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3256b-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="3256b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="3256b-108">Attribute</span></span>

|           | <span data-ttu-id="3256b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3256b-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="3256b-110">**key**</span><span class="sxs-lookup"><span data-stu-id="3256b-110">**key**</span></span>   | <span data-ttu-id="3256b-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3256b-111">Required attribute.</span></span><br><br><span data-ttu-id="3256b-112">Specifica il nome dell'impostazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="3256b-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="3256b-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="3256b-113">Parent element</span></span>

| <span data-ttu-id="3256b-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3256b-114">Element</span></span> | <span data-ttu-id="3256b-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3256b-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="3256b-116">SectionName > elemento  **\<** </span><span class="sxs-lookup"><span data-stu-id="3256b-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="3256b-117">Definisce le impostazioni per le sezioni di configurazione personalizzate <xref:System.Configuration.NameValueSectionHandler> che <xref:System.Configuration.DictionarySectionHandler> usano le classi e.</span><span class="sxs-lookup"><span data-stu-id="3256b-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3256b-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3256b-118">Child elements</span></span>

<span data-ttu-id="3256b-119">Nessuna</span><span class="sxs-lookup"><span data-stu-id="3256b-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="3256b-120">Note</span><span class="sxs-lookup"><span data-stu-id="3256b-120">Remarks</span></span>

<span data-ttu-id="3256b-121">È possibile usare l'  **\<elemento remove >** per rimuovere le impostazioni dall'applicazione definite a un livello superiore nella gerarchia dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="3256b-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="3256b-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="3256b-122">Example</span></span>

<span data-ttu-id="3256b-123">Nell'esempio seguente viene illustrato come utilizzare l'  **\<elemento remove >** in un file di configurazione dell'applicazione per rimuovere le impostazioni definite in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="3256b-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="3256b-124">Nel codice del file di configurazione del computer seguente `key1` viene dichiarata la sezione  **\<>** e vengono aggiunte `key2`due impostazioni:</span><span class="sxs-lookup"><span data-stu-id="3256b-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="3256b-125">Il codice del file di configurazione dell'applicazione `key2` seguente consente di rimuovere l'impostazione dall'  **\<area >** :</span><span class="sxs-lookup"><span data-stu-id="3256b-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="3256b-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="3256b-126">Configuration file</span></span>

<span data-ttu-id="3256b-127">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3256b-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="3256b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3256b-128">See also</span></span>

- [<span data-ttu-id="3256b-129">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3256b-129">Configuration file schema for the .NET Framework</span></span>](index.md)
