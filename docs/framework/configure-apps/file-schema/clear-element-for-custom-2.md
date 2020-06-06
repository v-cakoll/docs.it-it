---
title: <clear>elemento per NameValueSectionHandler e DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214747"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="6a643-102">\<clear>elemento per NameValueSectionHandler e DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="6a643-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="6a643-103">Cancella tutte le impostazioni definite in precedenza in una sezione.</span><span class="sxs-lookup"><span data-stu-id="6a643-103">Clears all previously defined settings in a section.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="6a643-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a643-104">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="6a643-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="6a643-105">Attributes</span></span>

<span data-ttu-id="6a643-106">nessuno</span><span class="sxs-lookup"><span data-stu-id="6a643-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="6a643-107">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="6a643-107">Parent element</span></span>

|     | <span data-ttu-id="6a643-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6a643-108">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="6a643-109">**\<sectionName>** Elemento</span><span class="sxs-lookup"><span data-stu-id="6a643-109">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="6a643-110">Definisce le impostazioni per le sezioni di configurazione personalizzate che usano le <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> classi e.</span><span class="sxs-lookup"><span data-stu-id="6a643-110">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6a643-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="6a643-111">Child elements</span></span>

<span data-ttu-id="6a643-112">nessuno</span><span class="sxs-lookup"><span data-stu-id="6a643-112">None</span></span>

## <a name="remarks"></a><span data-ttu-id="6a643-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6a643-113">Remarks</span></span>

<span data-ttu-id="6a643-114">È possibile utilizzare l' **\<clear>** elemento per rimuovere tutte le impostazioni dall'applicazione definite a un livello superiore nella gerarchia dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6a643-114">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="6a643-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a643-115">Example</span></span>

<span data-ttu-id="6a643-116">Questo esempio definisce un file di configurazione del computer e un file di configurazione dell'applicazione e Mostra come usare l' **\<clear>** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="6a643-116">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="6a643-117">Il seguente codice del file di configurazione del computer dichiara la sezione **\<mySection>** :</span><span class="sxs-lookup"><span data-stu-id="6a643-117">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="6a643-118">Il codice del file di configurazione dell'applicazione seguente consente di rimuovere tutte le impostazioni da **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="6a643-118">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="6a643-119">L'applicazione non è in grado di recuperare le impostazioni dichiarate nella **\<mySection>** sezione del file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="6a643-119">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="6a643-120">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="6a643-120">Configuration file</span></span>

<span data-ttu-id="6a643-121">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6a643-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a643-122">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6a643-122">See also</span></span>

- [<span data-ttu-id="6a643-123">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6a643-123">Configuration file schema for the .NET Framework</span></span>](index.md)
