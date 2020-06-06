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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153730"
---
# <a name="section-element"></a><span data-ttu-id="84cdf-102">Elemento \<section></span><span class="sxs-lookup"><span data-stu-id="84cdf-102">\<section> element</span></span>

<span data-ttu-id="84cdf-103">Contiene una dichiarazione della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="84cdf-103">Contains a configuration section declaration.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**

## <a name="syntax"></a><span data-ttu-id="84cdf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84cdf-104">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="84cdf-105">Attributi richiesti</span><span class="sxs-lookup"><span data-stu-id="84cdf-105">Required attributes</span></span>

|           | <span data-ttu-id="84cdf-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cdf-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="84cdf-107">**nome**</span><span class="sxs-lookup"><span data-stu-id="84cdf-107">**name**</span></span>  | <span data-ttu-id="84cdf-108">Specifica il nome della sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="84cdf-108">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="84cdf-109">**type**</span><span class="sxs-lookup"><span data-stu-id="84cdf-109">**type**</span></span>  | <span data-ttu-id="84cdf-110">Specifica il nome della classe del gestore della sezione di configurazione che legge la sezione dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="84cdf-110">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="84cdf-111">Il valore del tipo ha la sintassi "Fully-Qualified-section-handler-Class-Name, Simple-assembly-name".</span><span class="sxs-lookup"><span data-stu-id="84cdf-111">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="84cdf-112">Il nome dell'assembly semplice è il nome del file radice senza l'estensione *dll* .</span><span class="sxs-lookup"><span data-stu-id="84cdf-112">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="84cdf-113">Attributi facoltativi</span><span class="sxs-lookup"><span data-stu-id="84cdf-113">Optional attributes</span></span>

<span data-ttu-id="84cdf-114">Gli attributi seguenti sono applicabili solo per le applicazioni ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="84cdf-114">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="84cdf-115">Il sistema di configurazione Ignora questi attributi per altri tipi di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="84cdf-115">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="84cdf-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cdf-116">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="84cdf-117">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="84cdf-117">**allowDefinition**</span></span> | <span data-ttu-id="84cdf-118">Specifica il file di configurazione in cui è possibile utilizzare la sezione.</span><span class="sxs-lookup"><span data-stu-id="84cdf-118">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="84cdf-119">Usare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="84cdf-119">Use one of the following values:</span></span><br><br><span data-ttu-id="84cdf-120">**Ovunque**</span><span class="sxs-lookup"><span data-stu-id="84cdf-120">**Everywhere**</span></span><br><span data-ttu-id="84cdf-121">Consente di utilizzare la sezione in qualsiasi file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="84cdf-121">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="84cdf-122">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="84cdf-122">This is the default.</span></span><br><span data-ttu-id="84cdf-123">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="84cdf-123">**MachineOnly**</span></span><br><span data-ttu-id="84cdf-124">Consente di utilizzare la sezione solo nel file di configurazione del computer (*Machine. config*).</span><span class="sxs-lookup"><span data-stu-id="84cdf-124">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="84cdf-125">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="84cdf-125">**MachineToApplication**</span></span><br><span data-ttu-id="84cdf-126">Consente di utilizzare la sezione nel file di configurazione del computer o nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="84cdf-126">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="84cdf-127">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="84cdf-127">**allowLocation**</span></span>   | <span data-ttu-id="84cdf-128">Determina se la sezione può essere utilizzata all'interno dell' **\<location>** elemento.</span><span class="sxs-lookup"><span data-stu-id="84cdf-128">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="84cdf-129">Usare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="84cdf-129">Use one of the following values:</span></span><br><br><span data-ttu-id="84cdf-130">**true**</span><span class="sxs-lookup"><span data-stu-id="84cdf-130">**true**</span></span><br><span data-ttu-id="84cdf-131">Consente di utilizzare la sezione all'interno dell' **\<location>** elemento.</span><span class="sxs-lookup"><span data-stu-id="84cdf-131">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="84cdf-132">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="84cdf-132">This is the default.</span></span><br><span data-ttu-id="84cdf-133">**false**</span><span class="sxs-lookup"><span data-stu-id="84cdf-133">**false**</span></span><br><span data-ttu-id="84cdf-134">Non consente l'utilizzo della sezione all'interno dell' **\<location>** elemento.</span><span class="sxs-lookup"><span data-stu-id="84cdf-134">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="84cdf-135">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="84cdf-135">Parent elements</span></span>

|     | <span data-ttu-id="84cdf-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84cdf-136">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="84cdf-137">**\<configSections>** Elemento</span><span class="sxs-lookup"><span data-stu-id="84cdf-137">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="84cdf-138">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="84cdf-138">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="84cdf-139">**\<sectionGroup>** Elemento</span><span class="sxs-lookup"><span data-stu-id="84cdf-139">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="84cdf-140">Definisce uno spazio dei nomi per le sezioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="84cdf-140">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="84cdf-141">Un **\<section>** elemento è un elemento figlio di uno **\<configSections>** o **\<sectionGroup>** ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="84cdf-141">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="84cdf-142">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="84cdf-142">Child elements</span></span>

<span data-ttu-id="84cdf-143">nessuno</span><span class="sxs-lookup"><span data-stu-id="84cdf-143">None</span></span>

## <a name="remarks"></a><span data-ttu-id="84cdf-144">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="84cdf-144">Remarks</span></span>

<span data-ttu-id="84cdf-145">La dichiarazione di una sezione di configurazione definisce essenzialmente un nuovo elemento per il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="84cdf-145">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="84cdf-146">Il nuovo elemento contiene impostazioni lette da un gestore della sezione di configurazione, ovvero una classe che implementa l' <xref:System.Configuration.IConfigurationSectionHandler> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="84cdf-146">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="84cdf-147">Gli attributi e gli elementi figlio di una sezione definita dipendono dal gestore della sezione usato per leggere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="84cdf-147">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="84cdf-148">La dichiarazione di un gestore della sezione di configurazione nel file *Machine. config* consente di usare la sezione di configurazione in qualsiasi file di configurazione dell'applicazione nel computer, a meno che l'attributo **allowDefinition** non specifichi diversamente.</span><span class="sxs-lookup"><span data-stu-id="84cdf-148">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="84cdf-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="84cdf-149">Example</span></span>

<span data-ttu-id="84cdf-150">Nell'esempio seguente viene illustrato come definire una sezione di configurazione e definire le impostazioni per la sezione:</span><span class="sxs-lookup"><span data-stu-id="84cdf-150">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="84cdf-151">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="84cdf-151">Configuration file</span></span>

<span data-ttu-id="84cdf-152">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="84cdf-152">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="84cdf-153">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="84cdf-153">See also</span></span>

- [<span data-ttu-id="84cdf-154">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="84cdf-154">Configuration file schema for the .NET Framework</span></span>](index.md)
