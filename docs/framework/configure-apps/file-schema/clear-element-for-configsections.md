---
title: Elemento <clear> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155427"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="9a9df-102">Elemento \<clear> per \<configSections></span><span class="sxs-lookup"><span data-stu-id="9a9df-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="9a9df-103">Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9a9df-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="9a9df-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="9a9df-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9a9df-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a9df-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="9a9df-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="9a9df-106">Attribute</span></span>

|           | <span data-ttu-id="9a9df-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a9df-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="9a9df-108">**nome**</span><span class="sxs-lookup"><span data-stu-id="9a9df-108">**name**</span></span>  | <span data-ttu-id="9a9df-109">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9a9df-109">Required attribute.</span></span><br><br><span data-ttu-id="9a9df-110">Specifica il nome della sezione o del gruppo di sezioni da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="9a9df-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="9a9df-111">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="9a9df-111">Parent element</span></span>

|     | <span data-ttu-id="9a9df-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a9df-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9a9df-113">**\<configSections>** Elemento</span><span class="sxs-lookup"><span data-stu-id="9a9df-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="9a9df-114">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9a9df-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9a9df-115">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9a9df-115">Child elements</span></span>

<span data-ttu-id="9a9df-116">nessuno</span><span class="sxs-lookup"><span data-stu-id="9a9df-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="9a9df-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9a9df-117">Remarks</span></span>

<span data-ttu-id="9a9df-118">L' **\<clear>** elemento rimuove tutti i gruppi di sezioni e sezioni dall'applicazione definiti in precedenza nel file di configurazione corrente o a un livello superiore nella gerarchia dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9a9df-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="9a9df-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a9df-119">Example</span></span>

<span data-ttu-id="9a9df-120">Questo esempio definisce un file di configurazione del computer e un file di configurazione dell'applicazione e Mostra come usare l' **\<clear>** elemento in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="9a9df-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="9a9df-121">Il seguente codice del file di configurazione del computer dichiara due sezioni, **\<sampleSection>** e **\<anotherSampleSection>** , che vengono lette prima del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="9a9df-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="9a9df-122">Il codice del file di configurazione dell'applicazione seguente cancella tutte le sezioni precedentemente dichiarate.</span><span class="sxs-lookup"><span data-stu-id="9a9df-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="9a9df-123">L'applicazione non può usare o recuperare le impostazioni in una delle sezioni dichiarate nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="9a9df-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="9a9df-124">Tuttavia, può utilizzare le impostazioni da **\<anotherSection>** perché si trova dopo l' **\<clear>** elemento.</span><span class="sxs-lookup"><span data-stu-id="9a9df-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="9a9df-125">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="9a9df-125">Configuration file</span></span>

<span data-ttu-id="9a9df-126">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a9df-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a9df-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9a9df-127">See also</span></span>

- [<span data-ttu-id="9a9df-128">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9a9df-128">Configuration file schema for the .NET Framework</span></span>](index.md)
