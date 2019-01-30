---
title: <clear> (elemento) per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d824ae828dd025f3292990facaa5e423add9c282
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254768"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="4c491-102">\<Cancella > (elemento) per \<configSections ></span><span class="sxs-lookup"><span data-stu-id="4c491-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="4c491-103">Cancella tutte le sezioni definite in precedenza e i gruppi.</span><span class="sxs-lookup"><span data-stu-id="4c491-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="4c491-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="4c491-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="4c491-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="4c491-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="4c491-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="4c491-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4c491-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c491-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="4c491-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="4c491-108">Attribute</span></span>

|           | <span data-ttu-id="4c491-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c491-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="4c491-110">**name**</span><span class="sxs-lookup"><span data-stu-id="4c491-110">**name**</span></span>  | <span data-ttu-id="4c491-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="4c491-111">Required attribute.</span></span><br><br><span data-ttu-id="4c491-112">Specifica il nome della sezione o il gruppo di sezioni da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="4c491-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="4c491-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="4c491-113">Parent element</span></span>

|     | <span data-ttu-id="4c491-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c491-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4c491-115">**\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="4c491-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="4c491-116">Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4c491-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="4c491-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4c491-117">Child elements</span></span>

<span data-ttu-id="4c491-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="4c491-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="4c491-119">Note</span><span class="sxs-lookup"><span data-stu-id="4c491-119">Remarks</span></span>

<span data-ttu-id="4c491-120">Il  **\<clear >** elemento rimuove tutte le sezioni e gruppi dall'applicazione che sono state definite in precedenza nel file di configurazione corrente o a un livello superiore nella gerarchia di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4c491-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="4c491-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c491-121">Example</span></span>

<span data-ttu-id="4c491-122">In questo esempio definisce un file di configurazione di computer e un file di configurazione dell'applicazione e viene illustrato come utilizzare il  **\<clear >** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza di file di configurazione macchina.</span><span class="sxs-lookup"><span data-stu-id="4c491-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="4c491-123">Il codice di file di configurazione macchina seguente dichiara due sezioni  **\<sampleSection >** e  **\<anotherSampleSection >**, che vengono lette prima che l'applicazione file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="4c491-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="4c491-124">Il codice di file di configurazione dell'applicazione seguente cancella tutte le sezioni dichiarate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4c491-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="4c491-125">L'applicazione non è possibile usare o recuperare le impostazioni in una delle sezioni che sono state dichiarate nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="4c491-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="4c491-126">Tuttavia, può usare le impostazioni dal  **\<tale sezione si trova >** perché segue il  **\<deselezionare >** elemento.</span><span class="sxs-lookup"><span data-stu-id="4c491-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="4c491-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="4c491-127">Configuration file</span></span>

<span data-ttu-id="4c491-128">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4c491-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c491-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c491-129">See also</span></span>

- [<span data-ttu-id="4c491-130">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4c491-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
