---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153730"
---
# <a name="section-element"></a><span data-ttu-id="ddd9f-102">\<sezione> elemento</span><span class="sxs-lookup"><span data-stu-id="ddd9f-102">\<section> element</span></span>

<span data-ttu-id="ddd9f-103">Contiene una dichiarazione di sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="ddd9f-104">[**\<>di configurazione**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ddd9f-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="ddd9f-105">&nbsp;&nbsp;[**\<>configSections**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="ddd9f-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="ddd9f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sezione>**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="ddd9f-107">[**\<>di configurazione**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ddd9f-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="ddd9f-108">&nbsp;&nbsp;[**\<>configSections**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="ddd9f-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="ddd9f-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>gruppo section**](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="ddd9f-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="ddd9f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sezione>**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ddd9f-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ddd9f-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="ddd9f-112">Attributi richiesti</span><span class="sxs-lookup"><span data-stu-id="ddd9f-112">Required attributes</span></span>

|           | <span data-ttu-id="ddd9f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddd9f-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ddd9f-114">**name**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-114">**name**</span></span>  | <span data-ttu-id="ddd9f-115">Specifica il nome della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="ddd9f-116">**type**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-116">**type**</span></span>  | <span data-ttu-id="ddd9f-117">Specifica il nome della classe del gestore della sezione di configurazione che legge la sezione dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="ddd9f-118">Il valore del tipo ha la sintassi "fully-qualified-section-handler-class-name, simple-assembly-name".</span><span class="sxs-lookup"><span data-stu-id="ddd9f-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="ddd9f-119">Il nome dell'assembly semplice è il nome del file radice senza l'estensione del file *DLL.*</span><span class="sxs-lookup"><span data-stu-id="ddd9f-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="ddd9f-120">Attributi facoltativi</span><span class="sxs-lookup"><span data-stu-id="ddd9f-120">Optional attributes</span></span>

<span data-ttu-id="ddd9f-121">Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="ddd9f-122">Il sistema di configurazione ignora questi attributi per altri tipi di applicazione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="ddd9f-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddd9f-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="ddd9f-124">**Allowdefinition**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-124">**allowDefinition**</span></span> | <span data-ttu-id="ddd9f-125">Specifica in quale file di configurazione è possibile utilizzare la sezione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="ddd9f-126">Usare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddd9f-126">Use one of the following values:</span></span><br><br><span data-ttu-id="ddd9f-127">**Ovunque**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-127">**Everywhere**</span></span><br><span data-ttu-id="ddd9f-128">Consente di utilizzare la sezione in qualsiasi file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="ddd9f-129">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-129">This is the default.</span></span><br><span data-ttu-id="ddd9f-130">**Solo computer**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-130">**MachineOnly**</span></span><br><span data-ttu-id="ddd9f-131">Consente di utilizzare la sezione solo nel file di configurazione del computer (*Machine.config*).</span><span class="sxs-lookup"><span data-stu-id="ddd9f-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="ddd9f-132">**MachineToApplication (Applicazione macchina)**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-132">**MachineToApplication**</span></span><br><span data-ttu-id="ddd9f-133">Consente di utilizzare la sezione nel file di configurazione del computer o nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="ddd9f-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-134">**allowLocation**</span></span>   | <span data-ttu-id="ddd9f-135">Determina se la sezione può essere utilizzata all'interno dell'elemento \*\* \<>posizione.\*\*</span><span class="sxs-lookup"><span data-stu-id="ddd9f-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="ddd9f-136">Usare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddd9f-136">Use one of the following values:</span></span><br><br><span data-ttu-id="ddd9f-137">**true**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-137">**true**</span></span><br><span data-ttu-id="ddd9f-138">Consente di utilizzare la sezione all'interno dell'elemento \*\* \<location>.\*\*</span><span class="sxs-lookup"><span data-stu-id="ddd9f-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="ddd9f-139">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-139">This is the default.</span></span><br><span data-ttu-id="ddd9f-140">**false**</span><span class="sxs-lookup"><span data-stu-id="ddd9f-140">**false**</span></span><br><span data-ttu-id="ddd9f-141">Non consente l'utilizzo della sezione all'interno dell'elemento \*\* \<location>.\*\*</span><span class="sxs-lookup"><span data-stu-id="ddd9f-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="ddd9f-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ddd9f-142">Parent elements</span></span>

|     | <span data-ttu-id="ddd9f-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddd9f-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ddd9f-144">\*\* \<configSections>\*\* Elemento</span><span class="sxs-lookup"><span data-stu-id="ddd9f-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="ddd9f-145">Contiene le dichiarazioni della sezione di configurazione e dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="ddd9f-146">\*\* \<sezione>gruppo\*\* Elemento</span><span class="sxs-lookup"><span data-stu-id="ddd9f-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="ddd9f-147">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="ddd9f-148">Un \*\* \<\*\* elemento>di sezione è un elemento figlio di \*\* \<configSections>\*\* o \*\* \<sectionGroup>\*\* ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="ddd9f-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ddd9f-149">Child elements</span></span>

<span data-ttu-id="ddd9f-150">nessuno</span><span class="sxs-lookup"><span data-stu-id="ddd9f-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ddd9f-151">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ddd9f-151">Remarks</span></span>

<span data-ttu-id="ddd9f-152">La dichiarazione di una sezione di configurazione definisce essenzialmente un nuovo elemento per il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="ddd9f-153">Il nuovo elemento contiene le impostazioni che un gestore <xref:System.Configuration.IConfigurationSectionHandler> della sezione di configurazione (ovvero, una classe che implementa l'interfaccia) legge.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="ddd9f-154">Gli attributi e gli elementi figlio di una sezione definita dipendono dal gestore di sezione utilizzato per leggere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="ddd9f-155">La dichiarazione di un gestore della sezione di configurazione nel file *Machine.config* consente di utilizzare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione in tale computer, a meno che l'attributo **allowDefinition** non specifichi diversamente.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="ddd9f-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddd9f-156">Example</span></span>

<span data-ttu-id="ddd9f-157">L'esempio seguente mostra come definire una sezione di configurazione e definire le impostazioni per tale sezione:The following example shows how to define a configuration section and define settings for that section:</span><span class="sxs-lookup"><span data-stu-id="ddd9f-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="ddd9f-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="ddd9f-158">Configuration file</span></span>

<span data-ttu-id="ddd9f-159">Questo elemento può essere utilizzato nei file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine.config*) e nei file *Web.config* che non si trovano a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ddd9f-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddd9f-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddd9f-160">See also</span></span>

- [<span data-ttu-id="ddd9f-161">Schema del file di configurazione per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ddd9f-161">Configuration file schema for the .NET Framework</span></span>](index.md)
