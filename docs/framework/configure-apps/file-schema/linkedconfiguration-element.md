---
title: Elemento <linkedConfiguration>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74087969"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="79ef5-102">Elemento \<linkedConfiguration></span><span class="sxs-lookup"><span data-stu-id="79ef5-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="79ef5-103">Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="79ef5-103">Specifies a configuration file to include.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**

## <a name="syntax"></a><span data-ttu-id="79ef5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79ef5-104">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="79ef5-105">Attributo</span><span class="sxs-lookup"><span data-stu-id="79ef5-105">Attribute</span></span>

|           | <span data-ttu-id="79ef5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79ef5-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="79ef5-107">**href**</span><span class="sxs-lookup"><span data-stu-id="79ef5-107">**href**</span></span>  | <span data-ttu-id="79ef5-108">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="79ef5-108">Required attribute.</span></span><br><br><span data-ttu-id="79ef5-109">URL del file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="79ef5-109">The URL of the configuration file to include.</span></span> <span data-ttu-id="79ef5-110">L'unico formato supportato per l'attributo **href** è `file://` .</span><span class="sxs-lookup"><span data-stu-id="79ef5-110">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="79ef5-111">I file locali e i file UNC sono supportati.</span><span class="sxs-lookup"><span data-stu-id="79ef5-111">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="79ef5-112">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="79ef5-112">Parent element</span></span>

|     | <span data-ttu-id="79ef5-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79ef5-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="79ef5-114">**\<assemblyBinding>** Elemento</span><span class="sxs-lookup"><span data-stu-id="79ef5-114">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="79ef5-115">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="79ef5-115">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="79ef5-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="79ef5-116">Child elements</span></span>

<span data-ttu-id="79ef5-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="79ef5-117">None</span></span>

## <a name="remarks"></a><span data-ttu-id="79ef5-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="79ef5-118">Remarks</span></span>

<span data-ttu-id="79ef5-119">L' **\<linkedConfiguration>** elemento semplifica la manutenzione degli assembly del componente.</span><span class="sxs-lookup"><span data-stu-id="79ef5-119">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="79ef5-120">Se una o più applicazioni utilizzano un assembly con un file di configurazione che risiede in un percorso noto, i file di configurazione delle applicazioni che utilizzano l'assembly possono utilizzare l' **\<linkedConfiguration>** elemento per includere il file di configurazione dell'assembly, anziché includere direttamente le informazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="79ef5-120">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="79ef5-121">Quando l'assembly del componente viene servito, l'aggiornamento del file di configurazione comune fornisce informazioni di configurazione aggiornate a tutte le applicazioni che utilizzano l'assembly.</span><span class="sxs-lookup"><span data-stu-id="79ef5-121">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="79ef5-122">L' **\<linkedConfiguration>** elemento non è supportato per le applicazioni con manifesti affiancati di Windows.</span><span class="sxs-lookup"><span data-stu-id="79ef5-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="79ef5-123">Le regole seguenti regolano l'utilizzo dei file di configurazione collegati:</span><span class="sxs-lookup"><span data-stu-id="79ef5-123">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="79ef5-124">Le impostazioni nei file di configurazione inclusi influiscono solo sui criteri di associazione del caricatore e vengono usate solo dal caricatore.</span><span class="sxs-lookup"><span data-stu-id="79ef5-124">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="79ef5-125">I file di configurazione inclusi possono avere impostazioni diverse dai criteri di associazione, ma tali impostazioni non hanno alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="79ef5-125">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="79ef5-126">L'unico formato supportato per l' `href` attributo è `file://` .</span><span class="sxs-lookup"><span data-stu-id="79ef5-126">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="79ef5-127">I file locali e i file UNC sono supportati.</span><span class="sxs-lookup"><span data-stu-id="79ef5-127">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="79ef5-128">Non esiste alcun vincolo sul numero di configurazioni collegate per ogni file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="79ef5-128">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="79ef5-129">Tutti i file di configurazione collegati vengono uniti per formare un file, in modo analogo al comportamento della `#include` direttiva in C/C++.</span><span class="sxs-lookup"><span data-stu-id="79ef5-129">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="79ef5-130">L' **\<linkedConfiguration>** elemento è consentito solo nei file di configurazione dell'applicazione, ma viene ignorato in *Machine. config*.</span><span class="sxs-lookup"><span data-stu-id="79ef5-130">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="79ef5-131">I riferimenti circolari vengono rilevati e terminati.</span><span class="sxs-lookup"><span data-stu-id="79ef5-131">Circular references are detected and terminated.</span></span> <span data-ttu-id="79ef5-132">Ovvero, se gli **\<linkedConfiguration>** elementi di una serie di file di configurazione formano un ciclo, il ciclo viene rilevato e arrestato.</span><span class="sxs-lookup"><span data-stu-id="79ef5-132">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="79ef5-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="79ef5-133">Example</span></span>

<span data-ttu-id="79ef5-134">Nell'esempio seguente viene illustrato come includere il file di configurazione dal disco rigido locale:</span><span class="sxs-lookup"><span data-stu-id="79ef5-134">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="79ef5-135">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="79ef5-135">See also</span></span>

- [<span data-ttu-id="79ef5-136">**\<assemblyBinding>** Elemento</span><span class="sxs-lookup"><span data-stu-id="79ef5-136">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="79ef5-137">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="79ef5-137">Configuration file schema for the .NET Framework</span></span>](index.md)
