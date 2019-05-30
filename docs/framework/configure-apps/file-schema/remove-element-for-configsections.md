---
title: Elemento <remove> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 7c0173879c692588cc2e15f0b14a5687bb0404fb
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300668"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="7a4bb-102">\<rimuovere > (elemento) per \<configSections ></span><span class="sxs-lookup"><span data-stu-id="7a4bb-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="7a4bb-103">Rimuove una sezione predefiniti o un gruppo di sezioni.</span><span class="sxs-lookup"><span data-stu-id="7a4bb-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="7a4bb-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7a4bb-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7a4bb-105">&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7a4bb-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="7a4bb-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="7a4bb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7a4bb-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a4bb-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="7a4bb-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="7a4bb-108">Attribute</span></span>

|           | <span data-ttu-id="7a4bb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a4bb-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7a4bb-110">**name**</span><span class="sxs-lookup"><span data-stu-id="7a4bb-110">**name**</span></span>  | <span data-ttu-id="7a4bb-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7a4bb-111">Required attribute.</span></span><br><br><span data-ttu-id="7a4bb-112">Specifica il nome della sezione o il gruppo di sezioni da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="7a4bb-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7a4bb-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="7a4bb-113">Parent element</span></span>

|     | <span data-ttu-id="7a4bb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a4bb-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7a4bb-115"> *\*\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="7a4bb-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="7a4bb-116">Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a4bb-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7a4bb-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7a4bb-117">Child elements</span></span>

<span data-ttu-id="7a4bb-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="7a4bb-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="7a4bb-119">Note</span><span class="sxs-lookup"><span data-stu-id="7a4bb-119">Remarks</span></span>

<span data-ttu-id="7a4bb-120">È possibile usare la  **\<rimuovere >** elemento da rimuovere sezioni e gruppi dall'applicazione che sono stati definiti a un livello superiore nella gerarchia di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a4bb-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="7a4bb-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a4bb-121">Example</span></span>

<span data-ttu-id="7a4bb-122">Nell'esempio seguente viene illustrato come utilizzare il  **\<rimuovere >** elemento in un file di configurazione dell'applicazione per rimuovere una sezione definita in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="7a4bb-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="7a4bb-123">Il codice di file di configurazione macchina seguente dichiara la sezione  **\<sampleSection >** :</span><span class="sxs-lookup"><span data-stu-id="7a4bb-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="7a4bb-124">Il codice di file di configurazione dell'applicazione seguente rimuove il  **\<sampleSection >** sezione.</span><span class="sxs-lookup"><span data-stu-id="7a4bb-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="7a4bb-125">Dopo la rimozione, l'applicazione non è possibile recuperare le impostazioni in  **\<sampleSection >** .</span><span class="sxs-lookup"><span data-stu-id="7a4bb-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="7a4bb-126">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="7a4bb-126">Configuration file</span></span>

<span data-ttu-id="7a4bb-127">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7a4bb-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a4bb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a4bb-128">See also</span></span>

- [<span data-ttu-id="7a4bb-129">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7a4bb-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
