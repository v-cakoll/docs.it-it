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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215253"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="d2fca-102">Elemento \<sectionGroup> per \<configSections></span><span class="sxs-lookup"><span data-stu-id="d2fca-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="d2fca-103">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d2fca-103">Defines a namespace for configuration sections.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**

## <a name="syntax"></a><span data-ttu-id="d2fca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2fca-104">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="d2fca-105">Attributo</span><span class="sxs-lookup"><span data-stu-id="d2fca-105">Attribute</span></span>

|           | <span data-ttu-id="d2fca-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2fca-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d2fca-107">**nome**</span><span class="sxs-lookup"><span data-stu-id="d2fca-107">**name**</span></span>  | <span data-ttu-id="d2fca-108">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d2fca-108">Required attribute.</span></span><br><br><span data-ttu-id="d2fca-109">Specifica il nome del gruppo di sezioni da definire.</span><span class="sxs-lookup"><span data-stu-id="d2fca-109">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d2fca-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="d2fca-110">Parent element</span></span>

|     | <span data-ttu-id="d2fca-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2fca-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d2fca-112">**\<configSections>** Elemento</span><span class="sxs-lookup"><span data-stu-id="d2fca-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="d2fca-113">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d2fca-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d2fca-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d2fca-114">Child elements</span></span>

|     | <span data-ttu-id="d2fca-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2fca-115">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="d2fca-116">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d2fca-116">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d2fca-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="d2fca-117">Remarks</span></span>

<span data-ttu-id="d2fca-118">Se si dichiara un gruppo di sezioni, viene creato un tag del contenitore per le sezioni di configurazione e si garantisce che non vi siano conflitti di denominazione con le sezioni di configurazione definite da un altro utente.</span><span class="sxs-lookup"><span data-stu-id="d2fca-118">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="d2fca-119">È possibile annidare **\<sectionGroup>** gli elementi l'uno all'interno dell'altro.</span><span class="sxs-lookup"><span data-stu-id="d2fca-119">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="d2fca-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="d2fca-120">Example</span></span>

<span data-ttu-id="d2fca-121">Nell'esempio seguente viene illustrato come dichiarare un gruppo di sezioni e dichiarare le sezioni all'interno di un gruppo di sezioni:</span><span class="sxs-lookup"><span data-stu-id="d2fca-121">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="d2fca-122">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d2fca-122">Configuration file</span></span>

<span data-ttu-id="d2fca-123">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d2fca-123">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2fca-124">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d2fca-124">See also</span></span>

- [<span data-ttu-id="d2fca-125">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d2fca-125">Configuration file schema for the .NET Framework</span></span>](index.md)
