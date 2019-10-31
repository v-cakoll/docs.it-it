---
title: Elemento <remove> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f57dc9279c107ce751f71c2998670ab992db162
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118432"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="df33b-102">\<rimuovere > elemento per \<configSections ></span><span class="sxs-lookup"><span data-stu-id="df33b-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="df33b-103">Rimuove una sezione o un gruppo di sezioni predefinito.</span><span class="sxs-lookup"><span data-stu-id="df33b-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="df33b-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="df33b-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="df33b-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="df33b-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="df33b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<rimuovi >**</span><span class="sxs-lookup"><span data-stu-id="df33b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="df33b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df33b-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="df33b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="df33b-108">Attribute</span></span>

|           | <span data-ttu-id="df33b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df33b-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="df33b-110">**name**</span><span class="sxs-lookup"><span data-stu-id="df33b-110">**name**</span></span>  | <span data-ttu-id="df33b-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="df33b-111">Required attribute.</span></span><br><br><span data-ttu-id="df33b-112">Specifica il nome della sezione o del gruppo di sezioni da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="df33b-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="df33b-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="df33b-113">Parent element</span></span>

|     | <span data-ttu-id="df33b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="df33b-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="df33b-115"> **\<configSections >** Elemento</span><span class="sxs-lookup"><span data-stu-id="df33b-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="df33b-116">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="df33b-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="df33b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="df33b-117">Child elements</span></span>

<span data-ttu-id="df33b-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="df33b-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="df33b-119">Note</span><span class="sxs-lookup"><span data-stu-id="df33b-119">Remarks</span></span>

<span data-ttu-id="df33b-120">È possibile utilizzare l'elemento **\<remove >** per rimuovere sezioni e gruppi di sezioni dall'applicazione definiti a un livello superiore nella gerarchia dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="df33b-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="df33b-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="df33b-121">Example</span></span>

<span data-ttu-id="df33b-122">Nell'esempio seguente viene illustrato come utilizzare l'elemento **\<remove >** in un file di configurazione dell'applicazione per rimuovere una sezione precedentemente definita nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="df33b-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="df33b-123">Il seguente codice del file di configurazione del computer dichiara la sezione **\<sampleSection >** :</span><span class="sxs-lookup"><span data-stu-id="df33b-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="df33b-124">Il codice del file di configurazione dell'applicazione seguente rimuove la sezione **\<> sampleSection** .</span><span class="sxs-lookup"><span data-stu-id="df33b-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="df33b-125">Dopo la rimozione, l'applicazione non è in grado di recuperare le impostazioni in **\<> sampleSection**.</span><span class="sxs-lookup"><span data-stu-id="df33b-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="df33b-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="df33b-126">Configuration file</span></span>

<span data-ttu-id="df33b-127">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="df33b-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="df33b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df33b-128">See also</span></span>

- [<span data-ttu-id="df33b-129">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="df33b-129">Configuration file schema for the .NET Framework</span></span>](index.md)
