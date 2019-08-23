---
title: Elemento <sectionGroup> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 4e28e8ccea1090e6a5704b541e09dc11681278ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920643"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="d48fc-102">\<elemento > sectionGroup per \<configSections ></span><span class="sxs-lookup"><span data-stu-id="d48fc-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="d48fc-103">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d48fc-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="d48fc-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d48fc-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="d48fc-105">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d48fc-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="d48fc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="d48fc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d48fc-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d48fc-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="d48fc-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="d48fc-108">Attribute</span></span>

|           | <span data-ttu-id="d48fc-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d48fc-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d48fc-110">**name**</span><span class="sxs-lookup"><span data-stu-id="d48fc-110">**name**</span></span>  | <span data-ttu-id="d48fc-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d48fc-111">Required attribute.</span></span><br><br><span data-ttu-id="d48fc-112">Specifica il nome del gruppo di sezioni da definire.</span><span class="sxs-lookup"><span data-stu-id="d48fc-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d48fc-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="d48fc-113">Parent element</span></span>

|     | <span data-ttu-id="d48fc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d48fc-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d48fc-115">elemento  **>\<configSections**</span><span class="sxs-lookup"><span data-stu-id="d48fc-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="d48fc-116">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d48fc-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d48fc-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d48fc-117">Child elements</span></span>

|     | <span data-ttu-id="d48fc-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d48fc-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d48fc-119"> **\<> sezione**</span><span class="sxs-lookup"><span data-stu-id="d48fc-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="d48fc-120">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d48fc-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d48fc-121">Note</span><span class="sxs-lookup"><span data-stu-id="d48fc-121">Remarks</span></span>

<span data-ttu-id="d48fc-122">Se si dichiara un gruppo di sezioni, viene creato un tag del contenitore per le sezioni di configurazione e si garantisce che non vi siano conflitti di denominazione con le sezioni di configurazione definite da un altro utente.</span><span class="sxs-lookup"><span data-stu-id="d48fc-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="d48fc-123">È possibile annidare  **\<sectionGroup >** gli elementi tra loro.</span><span class="sxs-lookup"><span data-stu-id="d48fc-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="d48fc-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="d48fc-124">Example</span></span>

<span data-ttu-id="d48fc-125">Nell'esempio seguente viene illustrato come dichiarare un gruppo di sezioni e dichiarare le sezioni all'interno di un gruppo di sezioni:</span><span class="sxs-lookup"><span data-stu-id="d48fc-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="d48fc-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d48fc-126">Configuration file</span></span>

<span data-ttu-id="d48fc-127">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d48fc-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d48fc-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d48fc-128">See also</span></span>

- [<span data-ttu-id="d48fc-129">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d48fc-129">Configuration file schema for the .NET Framework</span></span>](index.md)
