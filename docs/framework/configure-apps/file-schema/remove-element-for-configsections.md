---
title: Elemento <remove> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154530"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="c16f4-102">Elemento \<remove> per \<configSections></span><span class="sxs-lookup"><span data-stu-id="c16f4-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="c16f4-103">Rimuove una sezione o un gruppo di sezioni predefinito.</span><span class="sxs-lookup"><span data-stu-id="c16f4-103">Removes a predefined section or section group.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="c16f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c16f4-104">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="c16f4-105">Attributo</span><span class="sxs-lookup"><span data-stu-id="c16f4-105">Attribute</span></span>

|           | <span data-ttu-id="c16f4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c16f4-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="c16f4-107">**nome**</span><span class="sxs-lookup"><span data-stu-id="c16f4-107">**name**</span></span>  | <span data-ttu-id="c16f4-108">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c16f4-108">Required attribute.</span></span><br><br><span data-ttu-id="c16f4-109">Specifica il nome della sezione o del gruppo di sezioni da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="c16f4-109">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="c16f4-110">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="c16f4-110">Parent element</span></span>

|     | <span data-ttu-id="c16f4-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c16f4-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c16f4-112">**\<configSections>** Elemento</span><span class="sxs-lookup"><span data-stu-id="c16f4-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="c16f4-113">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c16f4-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c16f4-114">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c16f4-114">Child elements</span></span>

<span data-ttu-id="c16f4-115">nessuno</span><span class="sxs-lookup"><span data-stu-id="c16f4-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="c16f4-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c16f4-116">Remarks</span></span>

<span data-ttu-id="c16f4-117">È possibile utilizzare l' **\<remove>** elemento per rimuovere sezioni e gruppi di sezioni dall'applicazione definiti a un livello superiore nella gerarchia dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c16f4-117">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="c16f4-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="c16f4-118">Example</span></span>

<span data-ttu-id="c16f4-119">Nell'esempio seguente viene illustrato come utilizzare l' **\<remove>** elemento in un file di configurazione dell'applicazione per rimuovere una sezione definita in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="c16f4-119">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="c16f4-120">Il seguente codice del file di configurazione del computer dichiara la sezione **\<sampleSection>** :</span><span class="sxs-lookup"><span data-stu-id="c16f4-120">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="c16f4-121">Il codice del file di configurazione dell'applicazione seguente rimuove la **\<sampleSection>** sezione.</span><span class="sxs-lookup"><span data-stu-id="c16f4-121">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="c16f4-122">Dopo la rimozione, l'applicazione non è in grado di recuperare le impostazioni in **\<sampleSection>** .</span><span class="sxs-lookup"><span data-stu-id="c16f4-122">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="c16f4-123">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="c16f4-123">Configuration file</span></span>

<span data-ttu-id="c16f4-124">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c16f4-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c16f4-125">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c16f4-125">See also</span></span>

- [<span data-ttu-id="c16f4-126">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c16f4-126">Configuration file schema for the .NET Framework</span></span>](index.md)
