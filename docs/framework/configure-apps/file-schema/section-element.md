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
ms.openlocfilehash: 8785523d664294e3ca3792fb0f84d739d1f1a376
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215721"
---
# <a name="section-element"></a><span data-ttu-id="b9d17-102">elemento > della sezione \<</span><span class="sxs-lookup"><span data-stu-id="b9d17-102">\<section> element</span></span>

<span data-ttu-id="b9d17-103">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9d17-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="b9d17-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9d17-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="b9d17-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b9d17-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="b9d17-106">&nbsp;&nbsp;&nbsp;**sezione\<** &nbsp;></span><span class="sxs-lookup"><span data-stu-id="b9d17-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="b9d17-107">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b9d17-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="b9d17-108">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b9d17-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="b9d17-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup**](sectiongroup-element-for-configsections.md) ></span><span class="sxs-lookup"><span data-stu-id="b9d17-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="b9d17-110">&nbsp;&nbsp;&nbsp;&nbsp; **&nbsp;&nbsp;\<** ></span><span class="sxs-lookup"><span data-stu-id="b9d17-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b9d17-111">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9d17-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="b9d17-112">Attributi richiesti</span><span class="sxs-lookup"><span data-stu-id="b9d17-112">Required attributes</span></span>

|           | <span data-ttu-id="b9d17-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9d17-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b9d17-114">**nome**</span><span class="sxs-lookup"><span data-stu-id="b9d17-114">**name**</span></span>  | <span data-ttu-id="b9d17-115">Specifica il nome della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9d17-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="b9d17-116">**type**</span><span class="sxs-lookup"><span data-stu-id="b9d17-116">**type**</span></span>  | <span data-ttu-id="b9d17-117">Specifica il nome della classe del gestore della sezione di configurazione che legge la sezione dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9d17-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="b9d17-118">Il valore del tipo ha la sintassi "Fully-Qualified-section-handler-Class-Name, Simple-assembly-name".</span><span class="sxs-lookup"><span data-stu-id="b9d17-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="b9d17-119">Il nome dell'assembly semplice è il nome del file radice senza l'estensione *dll* .</span><span class="sxs-lookup"><span data-stu-id="b9d17-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="b9d17-120">Attributi facoltativi</span><span class="sxs-lookup"><span data-stu-id="b9d17-120">Optional attributes</span></span>

<span data-ttu-id="b9d17-121">Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b9d17-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="b9d17-122">Il sistema di configurazione Ignora questi attributi per altri tipi di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b9d17-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="b9d17-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9d17-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="b9d17-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="b9d17-124">**allowDefinition**</span></span> | <span data-ttu-id="b9d17-125">Specifica il file di configurazione in cui è possibile utilizzare la sezione.</span><span class="sxs-lookup"><span data-stu-id="b9d17-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="b9d17-126">Usare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9d17-126">Use one of the following values:</span></span><br><br><span data-ttu-id="b9d17-127">**Ovunque**</span><span class="sxs-lookup"><span data-stu-id="b9d17-127">**Everywhere**</span></span><br><span data-ttu-id="b9d17-128">Consente di utilizzare la sezione in qualsiasi file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9d17-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="b9d17-129">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="b9d17-129">This is the default.</span></span><br><span data-ttu-id="b9d17-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="b9d17-130">**MachineOnly**</span></span><br><span data-ttu-id="b9d17-131">Consente di utilizzare la sezione solo nel file di configurazione del computer (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="b9d17-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="b9d17-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="b9d17-132">**MachineToApplication**</span></span><br><span data-ttu-id="b9d17-133">Consente di utilizzare la sezione nel file di configurazione del computer o nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b9d17-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="b9d17-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="b9d17-134">**allowLocation**</span></span>   | <span data-ttu-id="b9d17-135">Determina se la sezione può essere utilizzata all'interno dell'elemento **>\<location** .</span><span class="sxs-lookup"><span data-stu-id="b9d17-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="b9d17-136">Usare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9d17-136">Use one of the following values:</span></span><br><br><span data-ttu-id="b9d17-137">**true**</span><span class="sxs-lookup"><span data-stu-id="b9d17-137">**true**</span></span><br><span data-ttu-id="b9d17-138">Consente di utilizzare la sezione all'interno della **posizione\<>** elemento.</span><span class="sxs-lookup"><span data-stu-id="b9d17-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="b9d17-139">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="b9d17-139">This is the default.</span></span><br><span data-ttu-id="b9d17-140">**false**</span><span class="sxs-lookup"><span data-stu-id="b9d17-140">**false**</span></span><br><span data-ttu-id="b9d17-141">Non consente l'utilizzo della sezione all'interno dell'elemento **>\<location** .</span><span class="sxs-lookup"><span data-stu-id="b9d17-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="b9d17-142">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="b9d17-142">Parent elements</span></span>

|     | <span data-ttu-id="b9d17-143">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b9d17-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b9d17-144"> **\<configSections >** Elemento</span><span class="sxs-lookup"><span data-stu-id="b9d17-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="b9d17-145">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b9d17-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="b9d17-146"> **\<sectionGroup >** Elemento</span><span class="sxs-lookup"><span data-stu-id="b9d17-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="b9d17-147">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9d17-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="b9d17-148">Una **sezione\<>** elemento è un elemento figlio di **\<configSections >** o **\<sectionGroup >** ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="b9d17-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="b9d17-149">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="b9d17-149">Child elements</span></span>

<span data-ttu-id="b9d17-150">nessuno</span><span class="sxs-lookup"><span data-stu-id="b9d17-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="b9d17-151">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b9d17-151">Remarks</span></span>

<span data-ttu-id="b9d17-152">La dichiarazione di una sezione di configurazione definisce essenzialmente un nuovo elemento per il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9d17-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="b9d17-153">Il nuovo elemento contiene le impostazioni lette da un gestore della sezione di configurazione, ovvero una classe che implementa l'interfaccia <xref:System.Configuration.IConfigurationSectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="b9d17-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="b9d17-154">Gli attributi e gli elementi figlio di una sezione definita dipendono dal gestore della sezione usato per leggere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b9d17-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="b9d17-155">La dichiarazione di un gestore della sezione di configurazione nel file *Machine. config* consente di usare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione nel computer, a meno che l'attributo **allowDefinition** non specifichi diversamente.</span><span class="sxs-lookup"><span data-stu-id="b9d17-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="b9d17-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9d17-156">Example</span></span>

<span data-ttu-id="b9d17-157">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per la sezione:</span><span class="sxs-lookup"><span data-stu-id="b9d17-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="b9d17-158">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="b9d17-158">Configuration file</span></span>

<span data-ttu-id="b9d17-159">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b9d17-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9d17-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9d17-160">See also</span></span>

- [<span data-ttu-id="b9d17-161">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b9d17-161">Configuration file schema for the .NET Framework</span></span>](index.md)
