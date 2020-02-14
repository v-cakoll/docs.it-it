---
title: Elemento <sectionGroup> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
ms.openlocfilehash: eb221027470fe6e485f8fcc4b939b71e4f219712
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215253"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="34756-102">\<elemento > sectionGroup per \<configSections ></span><span class="sxs-lookup"><span data-stu-id="34756-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="34756-103">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="34756-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="34756-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34756-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="34756-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="34756-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="34756-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="34756-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="34756-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34756-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="34756-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="34756-108">Attribute</span></span>

|           | <span data-ttu-id="34756-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34756-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="34756-110">**nome**</span><span class="sxs-lookup"><span data-stu-id="34756-110">**name**</span></span>  | <span data-ttu-id="34756-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="34756-111">Required attribute.</span></span><br><br><span data-ttu-id="34756-112">Specifica il nome del gruppo di sezioni da definire.</span><span class="sxs-lookup"><span data-stu-id="34756-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="34756-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="34756-113">Parent element</span></span>

|     | <span data-ttu-id="34756-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34756-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="34756-115"> **\<configSections >** Elemento</span><span class="sxs-lookup"><span data-stu-id="34756-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="34756-116">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="34756-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="34756-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="34756-117">Child elements</span></span>

|     | <span data-ttu-id="34756-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34756-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="34756-119"> **\<sezione >** </span><span class="sxs-lookup"><span data-stu-id="34756-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="34756-120">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="34756-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="34756-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="34756-121">Remarks</span></span>

<span data-ttu-id="34756-122">Se si dichiara un gruppo di sezioni, viene creato un tag del contenitore per le sezioni di configurazione e si garantisce che non vi siano conflitti di denominazione con le sezioni di configurazione definite da un altro utente.</span><span class="sxs-lookup"><span data-stu-id="34756-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="34756-123">È possibile annidare\<elementi di **> sectionGroup** all'interno dell'altro.</span><span class="sxs-lookup"><span data-stu-id="34756-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="34756-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="34756-124">Example</span></span>

<span data-ttu-id="34756-125">Nell'esempio seguente viene illustrato come dichiarare un gruppo di sezioni e dichiarare le sezioni all'interno di un gruppo di sezioni:</span><span class="sxs-lookup"><span data-stu-id="34756-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="34756-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="34756-126">Configuration file</span></span>

<span data-ttu-id="34756-127">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="34756-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="34756-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34756-128">See also</span></span>

- [<span data-ttu-id="34756-129">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="34756-129">Configuration file schema for the .NET Framework</span></span>](index.md)
