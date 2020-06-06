---
title: <remove>elemento per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214765"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="80523-102">\<remove>elemento per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="80523-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="80523-103">Rimuove un'impostazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="80523-103">Removes a previously defined setting.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="80523-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80523-104">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="80523-105">Attributo</span><span class="sxs-lookup"><span data-stu-id="80523-105">Attribute</span></span>

|           | <span data-ttu-id="80523-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80523-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="80523-107">**key**</span><span class="sxs-lookup"><span data-stu-id="80523-107">**key**</span></span>   | <span data-ttu-id="80523-108">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="80523-108">Required attribute.</span></span><br><br><span data-ttu-id="80523-109">Specifica il nome dell'impostazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="80523-109">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="80523-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="80523-110">Parent element</span></span>

| <span data-ttu-id="80523-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="80523-111">Element</span></span> | <span data-ttu-id="80523-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80523-112">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="80523-113">**\<sectionName>** Elemento</span><span class="sxs-lookup"><span data-stu-id="80523-113">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="80523-114">Definisce le impostazioni per le sezioni di configurazione personalizzate che usano le <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> classi e.</span><span class="sxs-lookup"><span data-stu-id="80523-114">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="80523-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="80523-115">Child elements</span></span>

<span data-ttu-id="80523-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="80523-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="80523-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="80523-117">Remarks</span></span>

<span data-ttu-id="80523-118">È possibile utilizzare l' **\<remove>** elemento per rimuovere le impostazioni dall'applicazione definite a un livello superiore nella gerarchia dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="80523-118">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="80523-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="80523-119">Example</span></span>

<span data-ttu-id="80523-120">Nell'esempio seguente viene illustrato come utilizzare l' **\<remove>** elemento in un file di configurazione dell'applicazione per rimuovere le impostazioni definite in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="80523-120">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="80523-121">Nel codice del file di configurazione del computer seguente viene dichiarata la sezione **\<mySection>** e vengono aggiunte due impostazioni `key1` `key2` :</span><span class="sxs-lookup"><span data-stu-id="80523-121">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="80523-122">Il codice del file di configurazione dell'applicazione seguente rimuove l' `key2` impostazione da **\<mySection>** :</span><span class="sxs-lookup"><span data-stu-id="80523-122">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="80523-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="80523-123">Configuration file</span></span>

<span data-ttu-id="80523-124">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="80523-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="80523-125">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="80523-125">See also</span></span>

- [<span data-ttu-id="80523-126">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="80523-126">Configuration file schema for the .NET Framework</span></span>](index.md)
