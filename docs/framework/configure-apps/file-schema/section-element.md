---
title: '&lt;sezione&gt; elemento'
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e7de6e5ce6415c58deeca14df74c26e24957054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="section-element"></a><span data-ttu-id="2787d-102">\<sezione > elemento</span><span class="sxs-lookup"><span data-stu-id="2787d-102">\<section> element</span></span>

<span data-ttu-id="2787d-103">Contiene una dichiarazione di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2787d-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="2787d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2787d-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="2787d-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="2787d-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="2787d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sezione >**</span><span class="sxs-lookup"><span data-stu-id="2787d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="2787d-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2787d-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="2787d-108">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="2787d-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="2787d-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="2787d-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="2787d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sezione >**</span><span class="sxs-lookup"><span data-stu-id="2787d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2787d-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2787d-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="2787d-112">Attributi obbligatori</span><span class="sxs-lookup"><span data-stu-id="2787d-112">Required attributes</span></span>

|           | <span data-ttu-id="2787d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2787d-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="2787d-114">**name**</span><span class="sxs-lookup"><span data-stu-id="2787d-114">**name**</span></span>  | <span data-ttu-id="2787d-115">Specifica il nome della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2787d-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="2787d-116">**type**</span><span class="sxs-lookup"><span data-stu-id="2787d-116">**type**</span></span>  | <span data-ttu-id="2787d-117">Specifica il nome della classe del gestore della sezione configurazione che consente di leggere la sezione dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2787d-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="2787d-118">Il valore del tipo presenta la sintassi "fully-qualified-section-handler-class-name, nome dell'assembly semplice".</span><span class="sxs-lookup"><span data-stu-id="2787d-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="2787d-119">Il nome semplice dell'assembly è il nome del file principale senza la *DLL* estensione di file.</span><span class="sxs-lookup"><span data-stu-id="2787d-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="2787d-120">Attributi facoltativi</span><span class="sxs-lookup"><span data-stu-id="2787d-120">Optional attributes</span></span>

<span data-ttu-id="2787d-121">Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2787d-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="2787d-122">Il sistema di configurazione ignora questi attributi per gli altri tipi di applicazione.</span><span class="sxs-lookup"><span data-stu-id="2787d-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="2787d-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2787d-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="2787d-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="2787d-124">**allowDefinition**</span></span> | <span data-ttu-id="2787d-125">Specifica il file di configurazione è possibile utilizzare la sezione in.</span><span class="sxs-lookup"><span data-stu-id="2787d-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="2787d-126">Usare uno dei valori indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="2787d-126">Use one of the following values:</span></span><br><br><span data-ttu-id="2787d-127">**Ovunque**</span><span class="sxs-lookup"><span data-stu-id="2787d-127">**Everywhere**</span></span><br><span data-ttu-id="2787d-128">Consente di essere usato in qualsiasi file di configurazione la sezione.</span><span class="sxs-lookup"><span data-stu-id="2787d-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="2787d-129">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2787d-129">This is the default.</span></span><br><span data-ttu-id="2787d-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="2787d-130">**MachineOnly**</span></span><br><span data-ttu-id="2787d-131">Consente la sezione da utilizzare solo nel file di configurazione del computer (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="2787d-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="2787d-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="2787d-132">**MachineToApplication**</span></span><br><span data-ttu-id="2787d-133">Consente la sezione da utilizzare nel file di configurazione del computer o il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2787d-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="2787d-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="2787d-134">**allowLocation**</span></span>   | <span data-ttu-id="2787d-135">Determina se la sezione può essere utilizzata all'interno di  **\<percorso >** elemento.</span><span class="sxs-lookup"><span data-stu-id="2787d-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="2787d-136">Usare uno dei valori indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="2787d-136">Use one of the following values:</span></span><br><br><span data-ttu-id="2787d-137">**true**</span><span class="sxs-lookup"><span data-stu-id="2787d-137">**true**</span></span><br><span data-ttu-id="2787d-138">Consente la sezione all'interno di  **\<percorso >** elemento.</span><span class="sxs-lookup"><span data-stu-id="2787d-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="2787d-139">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2787d-139">This is the default.</span></span><br><span data-ttu-id="2787d-140">**false**</span><span class="sxs-lookup"><span data-stu-id="2787d-140">**false**</span></span><br><span data-ttu-id="2787d-141">Non consente la sezione all'interno di  **\<percorso >** elemento.</span><span class="sxs-lookup"><span data-stu-id="2787d-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="2787d-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2787d-142">Parent elements</span></span>

|     | <span data-ttu-id="2787d-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2787d-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2787d-144">**\<configSections >** elemento</span><span class="sxs-lookup"><span data-stu-id="2787d-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="2787d-145">Contiene le dichiarazioni dello spazio dei nomi e di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2787d-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="2787d-146">**\<sectionGroup >** elemento</span><span class="sxs-lookup"><span data-stu-id="2787d-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="2787d-147">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2787d-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="2787d-148">Oggetto  **\<sezione >** elemento è un elemento figlio di uno  **\<configSections >** o  **\<sectionGroup >** ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="2787d-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="2787d-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2787d-149">Child elements</span></span>

<span data-ttu-id="2787d-150">nessuno</span><span class="sxs-lookup"><span data-stu-id="2787d-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="2787d-151">Note</span><span class="sxs-lookup"><span data-stu-id="2787d-151">Remarks</span></span>

<span data-ttu-id="2787d-152">La dichiarazione essenzialmente di una sezione di configurazione definisce un nuovo elemento per il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2787d-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="2787d-153">Il nuovo elemento contiene le impostazioni di gestore della sezione di configurazione (vale a dire, una classe che implementa il <xref:System.Configuration.IConfigurationSectionHandler> interface) legge.</span><span class="sxs-lookup"><span data-stu-id="2787d-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="2787d-154">Gli attributi e gli elementi figlio di una sezione che definire dipendono dal gestore della sezione utilizzato per la lettura delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2787d-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="2787d-155">Dichiarazione di un gestore della sezione di configurazione nel *Machine. config* file consente di utilizzare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione nel computer, a meno che il **allowDefinition**attributo specifica in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="2787d-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="2787d-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="2787d-156">Example</span></span>

<span data-ttu-id="2787d-157">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e impostazioni per la sezione:</span><span class="sxs-lookup"><span data-stu-id="2787d-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="2787d-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="2787d-158">Configuration file</span></span>

<span data-ttu-id="2787d-159">Questo elemento può essere usato nel file di configurazione dell'applicazione, i file di configurazione macchina (*Machine. config*), e *Web. config* file che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2787d-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2787d-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2787d-160">See also</span></span>

[<span data-ttu-id="2787d-161">Schema di file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2787d-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
