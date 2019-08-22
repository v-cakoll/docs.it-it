---
title: <codeBase> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: a06daa0b2aa5374c9959cbbe778d62856819a40e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663859"
---
# <a name="codebase-element"></a><span data-ttu-id="2861f-102">\<Elemento codeBase ></span><span class="sxs-lookup"><span data-stu-id="2861f-102">\<codeBase> Element</span></span>

<span data-ttu-id="2861f-103">Specifica la posizione in cui il Common Language Runtime può trovare un assembly.</span><span class="sxs-lookup"><span data-stu-id="2861f-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="2861f-104">\<Configuration > \<Runtime > \<assembly > \<dependentAssembly > \<codebase ></span><span class="sxs-lookup"><span data-stu-id="2861f-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span></span>

## <a name="syntax"></a><span data-ttu-id="2861f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2861f-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2861f-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2861f-106">Attributes and Elements</span></span>

<span data-ttu-id="2861f-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2861f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2861f-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="2861f-108">Attributes</span></span>

|<span data-ttu-id="2861f-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="2861f-109">Attribute</span></span>|<span data-ttu-id="2861f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2861f-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="2861f-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2861f-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="2861f-112">Specifica l'URL in cui il runtime è in grado di trovare la versione specificata dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2861f-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="2861f-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="2861f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2861f-114">Specifica la versione dell'assembly a cui si applica la codebase.</span><span class="sxs-lookup"><span data-stu-id="2861f-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="2861f-115">Il formato di un numero di versione dell'assembly è *Major. minor. Build.* Revision.</span><span class="sxs-lookup"><span data-stu-id="2861f-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="2861f-116">Attributo Version</span><span class="sxs-lookup"><span data-stu-id="2861f-116">version Attribute</span></span>

|<span data-ttu-id="2861f-117">Valore</span><span class="sxs-lookup"><span data-stu-id="2861f-117">Value</span></span>|<span data-ttu-id="2861f-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2861f-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="2861f-119">I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="2861f-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="2861f-120">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="2861f-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2861f-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2861f-121">Child Elements</span></span>

<span data-ttu-id="2861f-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2861f-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2861f-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2861f-123">Parent Elements</span></span>

|<span data-ttu-id="2861f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="2861f-124">Element</span></span>|<span data-ttu-id="2861f-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2861f-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="2861f-126">Definisce una raccolta di provider di compilazione utilizzati per compilare file di risorse personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2861f-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="2861f-127">Possono essere presenti più provider di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2861f-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="2861f-128">Configura tutte le impostazioni di compilazione utilizzate da ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2861f-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="2861f-129">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2861f-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="2861f-130">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2861f-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2861f-131">Note</span><span class="sxs-lookup"><span data-stu-id="2861f-131">Remarks</span></span>

<span data-ttu-id="2861f-132">Affinché il runtime usi l'  **\<impostazione codebase >** in un file di configurazione del computer o in un file dei criteri editore, il file deve anche reindirizzare la versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2861f-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="2861f-133">I file di configurazione dell'applicazione possono avere un'impostazione codebase senza reindirizzamento della versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="2861f-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="2861f-134">Dopo aver determinato quale versione dell'assembly utilizzare, il runtime applica l'impostazione codebase dal file che determina la versione.</span><span class="sxs-lookup"><span data-stu-id="2861f-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="2861f-135">Se non è indicata alcuna codebase, il runtime esegue il probe per l'assembly nel modo consueto.</span><span class="sxs-lookup"><span data-stu-id="2861f-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="2861f-136">Se l'assembly ha un nome sicuro, l'impostazione codebase può trovarsi in qualsiasi punto della rete Intranet locale o Internet.</span><span class="sxs-lookup"><span data-stu-id="2861f-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="2861f-137">Se l'assembly è un assembly privato, l'impostazione codebase deve essere un percorso relativo alla directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2861f-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="2861f-138">Per gli assembly senza nome sicuro, la versione viene ignorata e il caricatore usa il primo \<aspetto di codebase \<> all'interno di dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="2861f-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="2861f-139">Se nel file di configurazione dell'applicazione è presente una voce che reindirizza il binding a un altro assembly, il reindirizzamento avrà la precedenza anche se la versione dell'assembly non corrisponde alla richiesta di associazione.</span><span class="sxs-lookup"><span data-stu-id="2861f-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="2861f-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="2861f-140">Example</span></span>

<span data-ttu-id="2861f-141">Nell'esempio seguente viene illustrato come specificare la posizione in cui il runtime può trovare un assembly.</span><span class="sxs-lookup"><span data-stu-id="2861f-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2861f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2861f-142">See also</span></span>

- [<span data-ttu-id="2861f-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="2861f-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2861f-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="2861f-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2861f-145">Specifica della posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="2861f-145">Specifying an Assembly's Location</span></span>](../../specify-assembly-location.md)
- [<span data-ttu-id="2861f-146">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="2861f-146">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
