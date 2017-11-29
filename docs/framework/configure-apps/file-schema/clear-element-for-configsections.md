---
title: '&lt;deselezionare&gt; elemento per &lt;configSections&gt;'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 70fc73c9e97274ac1165950038ee509fa8f2f9c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="059bb-102">\<Deselezionare > elemento per \<configSections ></span><span class="sxs-lookup"><span data-stu-id="059bb-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="059bb-103">Cancella tutte le sezioni definite in precedenza e i gruppi di sezioni.</span><span class="sxs-lookup"><span data-stu-id="059bb-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="059bb-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="059bb-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="059bb-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="059bb-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="059bb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Deselezionare >**</span><span class="sxs-lookup"><span data-stu-id="059bb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="059bb-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="059bb-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="059bb-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="059bb-108">Attribute</span></span>

|           | <span data-ttu-id="059bb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="059bb-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="059bb-110">**name**</span><span class="sxs-lookup"><span data-stu-id="059bb-110">**name**</span></span>  | <span data-ttu-id="059bb-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="059bb-111">Required attribute.</span></span><br><br><span data-ttu-id="059bb-112">Specifica il nome della sezione o del gruppo di sezione da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="059bb-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="059bb-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="059bb-113">Parent element</span></span>

|     | <span data-ttu-id="059bb-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="059bb-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="059bb-115">**\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="059bb-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="059bb-116">Contiene le dichiarazioni dello spazio dei nomi e di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="059bb-116">Contains configuration section and namespace declarations.</span></span> |

# <a name="child-elements"></a><span data-ttu-id="059bb-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="059bb-117">Child elements</span></span>

<span data-ttu-id="059bb-118">Nessuno</span><span class="sxs-lookup"><span data-stu-id="059bb-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="059bb-119">Note</span><span class="sxs-lookup"><span data-stu-id="059bb-119">Remarks</span></span>

<span data-ttu-id="059bb-120">Il  **\<deselezionare >** elemento rimuove tutte le sezioni e gruppi dall'applicazione che sono state definite nel file di configurazione corrente o a un livello superiore nella gerarchia di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="059bb-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="059bb-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="059bb-121">Example</span></span>

<span data-ttu-id="059bb-122">In questo esempio definisce un file di configurazione del computer e un file di configurazione dell'applicazione e viene illustrato come utilizzare il  **\<deselezionare >** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza di file di configurazione di computer.</span><span class="sxs-lookup"><span data-stu-id="059bb-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="059bb-123">Nel seguente codice di file di configurazione di computer vengono dichiarate due sezioni,  **\<sampleSection >** e  **\<anotherSampleSection >**, che vengono lette prima che l'applicazione file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="059bb-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="059bb-124">Il seguente codice di file di configurazione dell'applicazione Cancella tutte le sezioni dichiarate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="059bb-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="059bb-125">L'applicazione non è possibile utilizzare o recuperare le impostazioni in una delle sezioni che sono state dichiarate nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="059bb-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="059bb-126">Tuttavia, è possibile utilizzare le impostazioni di  **\<tale sezione si trova >** perché proviene dopo il  **\<deselezionare >** elemento.</span><span class="sxs-lookup"><span data-stu-id="059bb-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="059bb-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="059bb-127">Configuration file</span></span>

<span data-ttu-id="059bb-128">Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="059bb-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="059bb-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="059bb-129">See also</span></span>

[<span data-ttu-id="059bb-130">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="059bb-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
