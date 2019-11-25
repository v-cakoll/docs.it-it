---
title: elemento <linkedConfiguration>
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
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087969"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="9d2a6-102">\<elemento > linkedConfiguration</span><span class="sxs-lookup"><span data-stu-id="9d2a6-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="9d2a6-103">Specifica un file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="9d2a6-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d2a6-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="9d2a6-105">&nbsp;&nbsp;[ **\<assembly >** ](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="9d2a6-105">&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="9d2a6-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="9d2a6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9d2a6-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d2a6-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="9d2a6-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="9d2a6-108">Attribute</span></span>

|           | <span data-ttu-id="9d2a6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d2a6-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="9d2a6-110">**href**</span><span class="sxs-lookup"><span data-stu-id="9d2a6-110">**href**</span></span>  | <span data-ttu-id="9d2a6-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-111">Required attribute.</span></span><br><br><span data-ttu-id="9d2a6-112">URL del file di configurazione da includere.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="9d2a6-113">L'unico formato supportato per l'attributo **href** è `file://`.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="9d2a6-114">I file locali e i file UNC sono supportati.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="9d2a6-115">Elemento padre</span><span class="sxs-lookup"><span data-stu-id="9d2a6-115">Parent element</span></span>

|     | <span data-ttu-id="9d2a6-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d2a6-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9d2a6-117"> **\<> di associazione** Elemento</span><span class="sxs-lookup"><span data-stu-id="9d2a6-117">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="9d2a6-118">Specifica i criteri di associazione degli assembly al livello di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9d2a6-119">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9d2a6-119">Child elements</span></span>

<span data-ttu-id="9d2a6-120">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9d2a6-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="9d2a6-121">Note</span><span class="sxs-lookup"><span data-stu-id="9d2a6-121">Remarks</span></span>

<span data-ttu-id="9d2a6-122">L'elemento **\<linkedConfiguration >** semplifica la manutenzione degli assembly dei componenti.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="9d2a6-123">Se una o più applicazioni utilizzano un assembly con un file di configurazione che risiede in un percorso noto, i file di configurazione delle applicazioni che utilizzano l'assembly possono utilizzare l'elemento **\<linkedConfiguration >** per includere il file di configurazione dell'assembly, anziché includere direttamente le informazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="9d2a6-124">Quando l'assembly del componente viene servito, l'aggiornamento del file di configurazione comune fornisce informazioni di configurazione aggiornate a tutte le applicazioni che utilizzano l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="9d2a6-125">L'elemento **\<linkedConfiguration >** non è supportato per le applicazioni con manifesti affiancati di Windows.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="9d2a6-126">Le regole seguenti regolano l'utilizzo dei file di configurazione collegati:</span><span class="sxs-lookup"><span data-stu-id="9d2a6-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="9d2a6-127">Le impostazioni nei file di configurazione inclusi influiscono solo sui criteri di associazione del caricatore e vengono usate solo dal caricatore.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="9d2a6-128">I file di configurazione inclusi possono avere impostazioni diverse dai criteri di associazione, ma tali impostazioni non hanno alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="9d2a6-129">L'unico formato supportato per l'attributo `href` è `file://`.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="9d2a6-130">I file locali e i file UNC sono supportati.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="9d2a6-131">Non esiste alcun vincolo sul numero di configurazioni collegate per ogni file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="9d2a6-132">Tutti i file di configurazione collegati vengono uniti per formare un file, in modo analogo al comportamento della direttiva `#include`C++in C/.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="9d2a6-133">L'elemento **\<> linkedConfiguration** è consentito solo nei file di configurazione dell'applicazione. viene ignorato in *Machine. config*.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="9d2a6-134">I riferimenti circolari vengono rilevati e terminati.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="9d2a6-135">Ovvero, se il **\<linkedConfiguration >** elementi di una serie di file di configurazione formano un ciclo, il ciclo viene rilevato e arrestato.</span><span class="sxs-lookup"><span data-stu-id="9d2a6-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="9d2a6-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d2a6-136">Example</span></span>

<span data-ttu-id="9d2a6-137">Nell'esempio seguente viene illustrato come includere il file di configurazione dal disco rigido locale:</span><span class="sxs-lookup"><span data-stu-id="9d2a6-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="9d2a6-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d2a6-138">See also</span></span>

- [<span data-ttu-id="9d2a6-139"> **\<> di associazione** Elemento</span><span class="sxs-lookup"><span data-stu-id="9d2a6-139">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="9d2a6-140">Schema del file di configurazione per il .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9d2a6-140">Configuration file schema for the .NET Framework</span></span>](index.md)
