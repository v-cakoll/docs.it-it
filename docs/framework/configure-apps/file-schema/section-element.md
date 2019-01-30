---
title: <section> elemento
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 58f823ce0c128f30e361b4a631d41286533b5f0f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259215"
---
# <a name="section-element"></a><span data-ttu-id="694fe-102">\<sezione > elemento</span><span class="sxs-lookup"><span data-stu-id="694fe-102">\<section> element</span></span>

<span data-ttu-id="694fe-103">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="694fe-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="694fe-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="694fe-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="694fe-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="694fe-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span><span class="sxs-lookup"><span data-stu-id="694fe-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="694fe-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="694fe-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="694fe-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="694fe-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="694fe-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="694fe-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="694fe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span><span class="sxs-lookup"><span data-stu-id="694fe-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="694fe-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="694fe-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="694fe-112">Attributi obbligatori</span><span class="sxs-lookup"><span data-stu-id="694fe-112">Required attributes</span></span>

|           | <span data-ttu-id="694fe-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="694fe-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="694fe-114">**name**</span><span class="sxs-lookup"><span data-stu-id="694fe-114">**name**</span></span>  | <span data-ttu-id="694fe-115">Specifica il nome della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="694fe-116">**type**</span><span class="sxs-lookup"><span data-stu-id="694fe-116">**type**</span></span>  | <span data-ttu-id="694fe-117">Specifica il nome della classe del gestore della sezione configurazione che legge la sezione dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="694fe-118">Il valore del tipo presenta la sintassi "fully-qualified-section-handler-class-name, simple-assembly-name".</span><span class="sxs-lookup"><span data-stu-id="694fe-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="694fe-119">Il nome semplice dell'assembly è il nome file radice senza il *DLL* estensione di file.</span><span class="sxs-lookup"><span data-stu-id="694fe-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="694fe-120">Attributi facoltativi</span><span class="sxs-lookup"><span data-stu-id="694fe-120">Optional attributes</span></span>

<span data-ttu-id="694fe-121">Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="694fe-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="694fe-122">Il sistema di configurazione ignora questi attributi per gli altri tipi di applicazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="694fe-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="694fe-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="694fe-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="694fe-124">**allowDefinition**</span></span> | <span data-ttu-id="694fe-125">Specifica la sezione può essere usata in quale file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="694fe-126">Usare uno dei valori indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="694fe-126">Use one of the following values:</span></span><br><br><span data-ttu-id="694fe-127">**Everywhere**</span><span class="sxs-lookup"><span data-stu-id="694fe-127">**Everywhere**</span></span><br><span data-ttu-id="694fe-128">Consente la sezione da usare in qualsiasi file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="694fe-129">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="694fe-129">This is the default.</span></span><br><span data-ttu-id="694fe-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="694fe-130">**MachineOnly**</span></span><br><span data-ttu-id="694fe-131">Consente la sezione da utilizzare solo nel file di configurazione del computer (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="694fe-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="694fe-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="694fe-132">**MachineToApplication**</span></span><br><span data-ttu-id="694fe-133">Consente la sezione da utilizzare nel file di configurazione del computer o il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="694fe-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="694fe-134">**allowLocation**</span></span>   | <span data-ttu-id="694fe-135">Determina se la sezione può essere utilizzata all'interno di  **\<location >** elemento.</span><span class="sxs-lookup"><span data-stu-id="694fe-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="694fe-136">Usare uno dei valori indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="694fe-136">Use one of the following values:</span></span><br><br><span data-ttu-id="694fe-137">**true**</span><span class="sxs-lookup"><span data-stu-id="694fe-137">**true**</span></span><br><span data-ttu-id="694fe-138">Consente la sezione da usare all'interno di  **\<location >** elemento.</span><span class="sxs-lookup"><span data-stu-id="694fe-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="694fe-139">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="694fe-139">This is the default.</span></span><br><span data-ttu-id="694fe-140">**false**</span><span class="sxs-lookup"><span data-stu-id="694fe-140">**false**</span></span><br><span data-ttu-id="694fe-141">Non consente la sezione da usare all'interno di  **\<location >** elemento.</span><span class="sxs-lookup"><span data-stu-id="694fe-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="694fe-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="694fe-142">Parent elements</span></span>

|     | <span data-ttu-id="694fe-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="694fe-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="694fe-144">**\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="694fe-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="694fe-145">Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="694fe-146">**\<sectionGroup >** elemento</span><span class="sxs-lookup"><span data-stu-id="694fe-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="694fe-147">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="694fe-148">Oggetto  **\<sezione >** è un elemento figlio di uno  **\<configSections >** oppure  **\<sectionGroup >** ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="694fe-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="694fe-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="694fe-149">Child elements</span></span>

<span data-ttu-id="694fe-150">nessuno</span><span class="sxs-lookup"><span data-stu-id="694fe-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="694fe-151">Note</span><span class="sxs-lookup"><span data-stu-id="694fe-151">Remarks</span></span>

<span data-ttu-id="694fe-152">Essenzialmente la dichiarazione di una sezione di configurazione definisce un nuovo elemento per il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="694fe-153">Il nuovo elemento contiene le impostazioni della sezione di gestore di configurazione (vale a dire, una classe che implementa il <xref:System.Configuration.IConfigurationSectionHandler> interface) legge.</span><span class="sxs-lookup"><span data-stu-id="694fe-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="694fe-154">Gli attributi e gli elementi figlio di una sezione che è definire variano a seconda del gestore della sezione utilizzato per la lettura delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="694fe-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="694fe-155">La dichiarazione di un gestore della sezione di configurazione nel *Machine. config* file consente di usare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione nello stesso computer, a meno che non la **allowDefinition**attributo specifichi diversamente.</span><span class="sxs-lookup"><span data-stu-id="694fe-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="694fe-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="694fe-156">Example</span></span>

<span data-ttu-id="694fe-157">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per tale sezione:</span><span class="sxs-lookup"><span data-stu-id="694fe-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="694fe-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="694fe-158">Configuration file</span></span>

<span data-ttu-id="694fe-159">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="694fe-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="694fe-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="694fe-160">See also</span></span>

- [<span data-ttu-id="694fe-161">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="694fe-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
