---
title: '&lt;sezione&gt; elemento'
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
ms.openlocfilehash: 295cb8ee77c3042dc5742fb23cf4bbcd085b4d36
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659215"
---
# <a name="section-element"></a><span data-ttu-id="27d39-102">\<sezione > elemento</span><span class="sxs-lookup"><span data-stu-id="27d39-102">\<section> element</span></span>

<span data-ttu-id="27d39-103">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="27d39-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="27d39-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="27d39-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="27d39-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="27d39-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span><span class="sxs-lookup"><span data-stu-id="27d39-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="27d39-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="27d39-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="27d39-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="27d39-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="27d39-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="27d39-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="27d39-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span><span class="sxs-lookup"><span data-stu-id="27d39-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="27d39-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27d39-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="27d39-112">Attributi obbligatori</span><span class="sxs-lookup"><span data-stu-id="27d39-112">Required attributes</span></span>

|           | <span data-ttu-id="27d39-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27d39-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="27d39-114">**name**</span><span class="sxs-lookup"><span data-stu-id="27d39-114">**name**</span></span>  | <span data-ttu-id="27d39-115">Specifica il nome della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="27d39-116">**type**</span><span class="sxs-lookup"><span data-stu-id="27d39-116">**type**</span></span>  | <span data-ttu-id="27d39-117">Specifica il nome della classe del gestore della sezione configurazione che legge la sezione dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="27d39-118">Il valore del tipo presenta la sintassi "fully-qualified-section-handler-class-name, simple-assembly-name".</span><span class="sxs-lookup"><span data-stu-id="27d39-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="27d39-119">Il nome semplice dell'assembly è il nome file radice senza il *DLL* estensione di file.</span><span class="sxs-lookup"><span data-stu-id="27d39-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="27d39-120">Attributi facoltativi</span><span class="sxs-lookup"><span data-stu-id="27d39-120">Optional attributes</span></span>

<span data-ttu-id="27d39-121">Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="27d39-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="27d39-122">Il sistema di configurazione ignora questi attributi per gli altri tipi di applicazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="27d39-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27d39-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="27d39-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="27d39-124">**allowDefinition**</span></span> | <span data-ttu-id="27d39-125">Specifica la sezione può essere usata in quale file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="27d39-126">Usare uno dei valori indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="27d39-126">Use one of the following values:</span></span><br><br><span data-ttu-id="27d39-127">**Everywhere**</span><span class="sxs-lookup"><span data-stu-id="27d39-127">**Everywhere**</span></span><br><span data-ttu-id="27d39-128">Consente la sezione da usare in qualsiasi file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="27d39-129">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="27d39-129">This is the default.</span></span><br><span data-ttu-id="27d39-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="27d39-130">**MachineOnly**</span></span><br><span data-ttu-id="27d39-131">Consente la sezione da utilizzare solo nel file di configurazione del computer (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="27d39-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="27d39-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="27d39-132">**MachineToApplication**</span></span><br><span data-ttu-id="27d39-133">Consente la sezione da utilizzare nel file di configurazione del computer o il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="27d39-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="27d39-134">**allowLocation**</span></span>   | <span data-ttu-id="27d39-135">Determina se la sezione può essere utilizzata all'interno di  **\<location >** elemento.</span><span class="sxs-lookup"><span data-stu-id="27d39-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="27d39-136">Usare uno dei valori indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="27d39-136">Use one of the following values:</span></span><br><br><span data-ttu-id="27d39-137">**true**</span><span class="sxs-lookup"><span data-stu-id="27d39-137">**true**</span></span><br><span data-ttu-id="27d39-138">Consente la sezione da usare all'interno di  **\<location >** elemento.</span><span class="sxs-lookup"><span data-stu-id="27d39-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="27d39-139">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="27d39-139">This is the default.</span></span><br><span data-ttu-id="27d39-140">**false**</span><span class="sxs-lookup"><span data-stu-id="27d39-140">**false**</span></span><br><span data-ttu-id="27d39-141">Non consente la sezione da usare all'interno di  **\<location >** elemento.</span><span class="sxs-lookup"><span data-stu-id="27d39-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="27d39-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="27d39-142">Parent elements</span></span>

|     | <span data-ttu-id="27d39-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27d39-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="27d39-144">**\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="27d39-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="27d39-145">Contiene le dichiarazioni dello spazio dei nomi e sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="27d39-146">**\<sectionGroup >** elemento</span><span class="sxs-lookup"><span data-stu-id="27d39-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="27d39-147">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="27d39-148">Oggetto  **\<sezione >** è un elemento figlio di uno  **\<configSections >** oppure  **\<sectionGroup >** ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="27d39-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="27d39-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="27d39-149">Child elements</span></span>

<span data-ttu-id="27d39-150">nessuno</span><span class="sxs-lookup"><span data-stu-id="27d39-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="27d39-151">Note</span><span class="sxs-lookup"><span data-stu-id="27d39-151">Remarks</span></span>

<span data-ttu-id="27d39-152">Essenzialmente la dichiarazione di una sezione di configurazione definisce un nuovo elemento per il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="27d39-153">Il nuovo elemento contiene le impostazioni della sezione di gestore di configurazione (vale a dire, una classe che implementa il <xref:System.Configuration.IConfigurationSectionHandler> interface) legge.</span><span class="sxs-lookup"><span data-stu-id="27d39-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="27d39-154">Gli attributi e gli elementi figlio di una sezione che è definire variano a seconda del gestore della sezione utilizzato per la lettura delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="27d39-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="27d39-155">La dichiarazione di un gestore della sezione di configurazione nel *Machine. config* file consente di usare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione nello stesso computer, a meno che non la **allowDefinition**attributo specifichi diversamente.</span><span class="sxs-lookup"><span data-stu-id="27d39-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="27d39-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="27d39-156">Example</span></span>

<span data-ttu-id="27d39-157">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per tale sezione:</span><span class="sxs-lookup"><span data-stu-id="27d39-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="27d39-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="27d39-158">Configuration file</span></span>

<span data-ttu-id="27d39-159">Questo elemento può essere usato nel file di configurazione dell'applicazione, file di configurazione computer (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27d39-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="27d39-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27d39-160">See also</span></span>

- [<span data-ttu-id="27d39-161">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="27d39-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
