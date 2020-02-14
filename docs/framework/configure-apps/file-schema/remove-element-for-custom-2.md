---
title: elemento <remove> per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214765"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="87817-102">\<rimuovere > elemento per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="87817-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="87817-103">Rimuove un'impostazione definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="87817-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="87817-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87817-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="87817-105">&nbsp;&nbsp;[ **\<sectionname >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="87817-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="87817-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<rimuovi >**</span><span class="sxs-lookup"><span data-stu-id="87817-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="87817-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87817-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="87817-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="87817-108">Attribute</span></span>

|           | <span data-ttu-id="87817-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87817-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="87817-110">**key**</span><span class="sxs-lookup"><span data-stu-id="87817-110">**key**</span></span>   | <span data-ttu-id="87817-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="87817-111">Required attribute.</span></span><br><br><span data-ttu-id="87817-112">Specifica il nome dell'impostazione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="87817-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="87817-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="87817-113">Parent element</span></span>

| <span data-ttu-id="87817-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="87817-114">Element</span></span> | <span data-ttu-id="87817-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87817-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="87817-116"> **\<sectionname >** Elemento</span><span class="sxs-lookup"><span data-stu-id="87817-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="87817-117">Definisce le impostazioni per le sezioni di configurazione personalizzate che usano le classi <xref:System.Configuration.NameValueSectionHandler> e <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="87817-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="87817-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="87817-118">Child elements</span></span>

<span data-ttu-id="87817-119">nessuno</span><span class="sxs-lookup"><span data-stu-id="87817-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="87817-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="87817-120">Remarks</span></span>

<span data-ttu-id="87817-121">È possibile usare l'elemento **\<remove >** per rimuovere le impostazioni dall'applicazione definite a un livello superiore nella gerarchia dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="87817-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="87817-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="87817-122">Example</span></span>

<span data-ttu-id="87817-123">Nell'esempio seguente viene illustrato come utilizzare il **\<rimuovere >** elemento in un file di configurazione dell'applicazione per rimuovere le impostazioni definite in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="87817-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="87817-124">Il seguente codice del file di configurazione del computer dichiara la sezione **\<sezione >** e aggiunge due impostazioni, `key1` e `key2`:</span><span class="sxs-lookup"><span data-stu-id="87817-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="87817-125">Il codice del file di configurazione dell'applicazione seguente rimuove l'impostazione `key2` da **\<sezione >** :</span><span class="sxs-lookup"><span data-stu-id="87817-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="87817-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="87817-126">Configuration file</span></span>

<span data-ttu-id="87817-127">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="87817-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="87817-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87817-128">See also</span></span>

- [<span data-ttu-id="87817-129">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="87817-129">Configuration file schema for the .NET Framework</span></span>](index.md)
