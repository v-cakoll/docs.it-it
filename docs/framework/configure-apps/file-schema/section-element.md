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
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 94f7709f4bd273515d9fcdd727354ec579c46207
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927223"
---
# <a name="section-element"></a><span data-ttu-id="d75d4-102">\<Section > elemento</span><span class="sxs-lookup"><span data-stu-id="d75d4-102">\<section> element</span></span>

<span data-ttu-id="d75d4-103">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d75d4-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="d75d4-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d75d4-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="d75d4-105">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d75d4-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="d75d4-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> sezione**</span><span class="sxs-lookup"><span data-stu-id="d75d4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="d75d4-107">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d75d4-107">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="d75d4-108">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d75d4-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="d75d4-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup>** ](sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="d75d4-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="d75d4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> sezione**</span><span class="sxs-lookup"><span data-stu-id="d75d4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d75d4-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d75d4-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="d75d4-112">Attributi obbligatori</span><span class="sxs-lookup"><span data-stu-id="d75d4-112">Required attributes</span></span>

|           | <span data-ttu-id="d75d4-113">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d75d4-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d75d4-114">**name**</span><span class="sxs-lookup"><span data-stu-id="d75d4-114">**name**</span></span>  | <span data-ttu-id="d75d4-115">Specifica il nome della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d75d4-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="d75d4-116">**type**</span><span class="sxs-lookup"><span data-stu-id="d75d4-116">**type**</span></span>  | <span data-ttu-id="d75d4-117">Specifica il nome della classe del gestore della sezione di configurazione che legge la sezione dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d75d4-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="d75d4-118">Il valore del tipo ha la sintassi "Fully-Qualified-section-handler-Class-Name, Simple-assembly-name".</span><span class="sxs-lookup"><span data-stu-id="d75d4-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="d75d4-119">Il nome dell'assembly semplice è il nome del file radice senza l'estensione *dll* .</span><span class="sxs-lookup"><span data-stu-id="d75d4-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="d75d4-120">Attributi facoltativi</span><span class="sxs-lookup"><span data-stu-id="d75d4-120">Optional attributes</span></span>

<span data-ttu-id="d75d4-121">Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d75d4-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="d75d4-122">Il sistema di configurazione Ignora questi attributi per altri tipi di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d75d4-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="d75d4-123">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d75d4-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="d75d4-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="d75d4-124">**allowDefinition**</span></span> | <span data-ttu-id="d75d4-125">Specifica il file di configurazione in cui è possibile utilizzare la sezione.</span><span class="sxs-lookup"><span data-stu-id="d75d4-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="d75d4-126">Usare uno dei valori indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="d75d4-126">Use one of the following values:</span></span><br><br><span data-ttu-id="d75d4-127">**Ovunque**</span><span class="sxs-lookup"><span data-stu-id="d75d4-127">**Everywhere**</span></span><br><span data-ttu-id="d75d4-128">Consente di utilizzare la sezione in qualsiasi file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d75d4-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="d75d4-129">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d75d4-129">This is the default.</span></span><br><span data-ttu-id="d75d4-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="d75d4-130">**MachineOnly**</span></span><br><span data-ttu-id="d75d4-131">Consente di utilizzare la sezione solo nel file di configurazione del computer (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="d75d4-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="d75d4-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="d75d4-132">**MachineToApplication**</span></span><br><span data-ttu-id="d75d4-133">Consente di utilizzare la sezione nel file di configurazione del computer o nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d75d4-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="d75d4-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="d75d4-134">**allowLocation**</span></span>   | <span data-ttu-id="d75d4-135">Determina se la sezione può essere utilizzata all'interno della  **\<posizione >** elemento.</span><span class="sxs-lookup"><span data-stu-id="d75d4-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="d75d4-136">Usare uno dei valori indicati di seguito.</span><span class="sxs-lookup"><span data-stu-id="d75d4-136">Use one of the following values:</span></span><br><br><span data-ttu-id="d75d4-137">**true**</span><span class="sxs-lookup"><span data-stu-id="d75d4-137">**true**</span></span><br><span data-ttu-id="d75d4-138">Consente di utilizzare la sezione all'interno della  **\<posizione >** elemento.</span><span class="sxs-lookup"><span data-stu-id="d75d4-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="d75d4-139">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d75d4-139">This is the default.</span></span><br><span data-ttu-id="d75d4-140">**false**</span><span class="sxs-lookup"><span data-stu-id="d75d4-140">**false**</span></span><br><span data-ttu-id="d75d4-141">Non consente l'utilizzo della sezione all'interno della  **\<posizione >** elemento.</span><span class="sxs-lookup"><span data-stu-id="d75d4-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="d75d4-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="d75d4-142">Parent elements</span></span>

|     | <span data-ttu-id="d75d4-143">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="d75d4-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d75d4-144">elemento  **>\<configSections**</span><span class="sxs-lookup"><span data-stu-id="d75d4-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="d75d4-145">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d75d4-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="d75d4-146">elemento  **>\<sectionGroup**</span><span class="sxs-lookup"><span data-stu-id="d75d4-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="d75d4-147">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d75d4-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="d75d4-148">**Una\<sezione >** elemento è un elemento  **\<figlio di configSections >** o  **\<sectionGroup >** ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="d75d4-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="d75d4-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="d75d4-149">Child elements</span></span>

<span data-ttu-id="d75d4-150">Nessuna</span><span class="sxs-lookup"><span data-stu-id="d75d4-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="d75d4-151">Note</span><span class="sxs-lookup"><span data-stu-id="d75d4-151">Remarks</span></span>

<span data-ttu-id="d75d4-152">La dichiarazione di una sezione di configurazione definisce essenzialmente un nuovo elemento per il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d75d4-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="d75d4-153">Il nuovo elemento contiene impostazioni lette da un gestore della sezione di configurazione, ovvero una classe che <xref:System.Configuration.IConfigurationSectionHandler> implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d75d4-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="d75d4-154">Gli attributi e gli elementi figlio di una sezione definita dipendono dal gestore della sezione usato per leggere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="d75d4-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="d75d4-155">La dichiarazione di un gestore della sezione di configurazione nel file *Machine. config* consente di usare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione nel computer, a meno che l'attributo **allowDefinition** non specifichi diversamente.</span><span class="sxs-lookup"><span data-stu-id="d75d4-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="d75d4-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="d75d4-156">Example</span></span>

<span data-ttu-id="d75d4-157">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per la sezione:</span><span class="sxs-lookup"><span data-stu-id="d75d4-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="d75d4-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="d75d4-158">Configuration file</span></span>

<span data-ttu-id="d75d4-159">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d75d4-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d75d4-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d75d4-160">See also</span></span>

- [<span data-ttu-id="d75d4-161">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d75d4-161">Configuration file schema for the .NET Framework</span></span>](index.md)
