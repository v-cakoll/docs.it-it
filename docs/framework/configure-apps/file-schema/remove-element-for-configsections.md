---
title: '&lt;rimuovere&gt; (elemento) per &lt;configSections&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 11a930120c375616d73faae68a6d6807c2f633cb
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307227"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="ed89b-102">\<rimuovere > (elemento) per \<configSections ></span><span class="sxs-lookup"><span data-stu-id="ed89b-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="ed89b-103">Rimuove una sezione predefiniti o un gruppo di sezioni.</span><span class="sxs-lookup"><span data-stu-id="ed89b-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="ed89b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ed89b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ed89b-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="ed89b-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="ed89b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="ed89b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ed89b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed89b-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="ed89b-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="ed89b-108">Attribute</span></span>

|           | <span data-ttu-id="ed89b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed89b-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ed89b-110">**name**</span><span class="sxs-lookup"><span data-stu-id="ed89b-110">**name**</span></span>  | <span data-ttu-id="ed89b-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ed89b-111">Required attribute.</span></span><br><br><span data-ttu-id="ed89b-112">Specifica il nome della sezione o il gruppo di sezioni da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="ed89b-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ed89b-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="ed89b-113">Parent element</span></span>

|     | <span data-ttu-id="ed89b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed89b-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ed89b-115">**\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="ed89b-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="ed89b-116">Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ed89b-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ed89b-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ed89b-117">Child elements</span></span>

<span data-ttu-id="ed89b-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="ed89b-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ed89b-119">Note</span><span class="sxs-lookup"><span data-stu-id="ed89b-119">Remarks</span></span>

<span data-ttu-id="ed89b-120">È possibile usare la  **\<rimuovere >** elemento da rimuovere sezioni e gruppi dall'applicazione che sono stati definiti a un livello superiore nella gerarchia di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ed89b-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="ed89b-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed89b-121">Example</span></span>

<span data-ttu-id="ed89b-122">Nell'esempio seguente viene illustrato come utilizzare il  **\<rimuovere >** elemento in un file di configurazione dell'applicazione per rimuovere una sezione definita in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="ed89b-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="ed89b-123">Il codice di file di configurazione macchina seguente dichiara la sezione  **\<sampleSection >**:</span><span class="sxs-lookup"><span data-stu-id="ed89b-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="ed89b-124">Il codice di file di configurazione dell'applicazione seguente rimuove il  **\<sampleSection >** sezione.</span><span class="sxs-lookup"><span data-stu-id="ed89b-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="ed89b-125">Dopo la rimozione, l'applicazione non è possibile recuperare le impostazioni in  **\<sampleSection >**.</span><span class="sxs-lookup"><span data-stu-id="ed89b-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ed89b-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ed89b-126">Configuration file</span></span>

<span data-ttu-id="ed89b-127">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ed89b-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed89b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed89b-128">See also</span></span>

[<span data-ttu-id="ed89b-129">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed89b-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
