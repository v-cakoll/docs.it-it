---
title: Elemento <clear> per <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: e8c9b0479bba839a74dff300f0766838b5d99c8d
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214834"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="81fd0-102">\<elemento clear > per \<configSections ></span><span class="sxs-lookup"><span data-stu-id="81fd0-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="81fd0-103">Cancella tutte le sezioni e i gruppi di sezioni definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="81fd0-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="81fd0-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="81fd0-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="81fd0-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="81fd0-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="81fd0-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<cancella >**</span><span class="sxs-lookup"><span data-stu-id="81fd0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="81fd0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81fd0-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="81fd0-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="81fd0-108">Attribute</span></span>

|           | <span data-ttu-id="81fd0-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81fd0-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="81fd0-110">**nome**</span><span class="sxs-lookup"><span data-stu-id="81fd0-110">**name**</span></span>  | <span data-ttu-id="81fd0-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="81fd0-111">Required attribute.</span></span><br><br><span data-ttu-id="81fd0-112">Specifica il nome della sezione o del gruppo di sezioni da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="81fd0-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="81fd0-113">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="81fd0-113">Parent element</span></span>

|     | <span data-ttu-id="81fd0-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="81fd0-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="81fd0-115"> **\<configSections >** Elemento</span><span class="sxs-lookup"><span data-stu-id="81fd0-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="81fd0-116">Contiene la sezione di configurazione e le dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="81fd0-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="81fd0-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="81fd0-117">Child elements</span></span>

<span data-ttu-id="81fd0-118">nessuno</span><span class="sxs-lookup"><span data-stu-id="81fd0-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="81fd0-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="81fd0-119">Remarks</span></span>

<span data-ttu-id="81fd0-120">L'elemento **\<clear >** rimuove tutte le sezioni e i gruppi di sezioni dall'applicazione definiti in precedenza nel file di configurazione corrente o a un livello superiore nella gerarchia dei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="81fd0-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="81fd0-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="81fd0-121">Example</span></span>

<span data-ttu-id="81fd0-122">Questo esempio definisce un file di configurazione del computer e un file di configurazione dell'applicazione e Mostra come usare l'elemento **\<clear >** in un file di configurazione dell'applicazione per cancellare le sezioni definite in precedenza nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="81fd0-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="81fd0-123">Il seguente codice del file di configurazione del computer dichiara due sezioni, **\<sampleSection >** e **\<anotherSampleSection >** , che vengono lette prima del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="81fd0-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

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

<span data-ttu-id="81fd0-124">Il codice del file di configurazione dell'applicazione seguente cancella tutte le sezioni precedentemente dichiarate.</span><span class="sxs-lookup"><span data-stu-id="81fd0-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="81fd0-125">L'applicazione non può usare o recuperare le impostazioni in una delle sezioni dichiarate nel file di configurazione del computer.</span><span class="sxs-lookup"><span data-stu-id="81fd0-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="81fd0-126">Tuttavia, può usare le impostazioni di **\<anotherSection >** perché si trova dopo l'elemento **\<Clear >** .</span><span class="sxs-lookup"><span data-stu-id="81fd0-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="81fd0-127">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="81fd0-127">Configuration file</span></span>

<span data-ttu-id="81fd0-128">Questo elemento può essere utilizzato nel file di configurazione dell'applicazione, nel file di configurazione del computer (*Machine. config*) e nei file *Web. config* che non sono a livello di directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="81fd0-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="81fd0-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81fd0-129">See also</span></span>

- [<span data-ttu-id="81fd0-130">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="81fd0-130">Configuration file schema for the .NET Framework</span></span>](index.md)
