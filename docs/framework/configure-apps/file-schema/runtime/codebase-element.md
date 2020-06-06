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
ms.openlocfilehash: 475b7df55ed509157c1da0aeb8f979de238c72b5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70971881"
---
# <a name="codebase-element"></a><span data-ttu-id="72692-102">\<codeBase> Elemento</span><span class="sxs-lookup"><span data-stu-id="72692-102">\<codeBase> Element</span></span>

<span data-ttu-id="72692-103">Specifica la posizione in cui il Common Language Runtime può trovare un assembly.</span><span class="sxs-lookup"><span data-stu-id="72692-103">Specifies where the common language runtime can find an assembly.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**

## <a name="syntax"></a><span data-ttu-id="72692-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72692-104">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="72692-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="72692-105">Attributes and Elements</span></span>

<span data-ttu-id="72692-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="72692-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="72692-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="72692-107">Attributes</span></span>

|<span data-ttu-id="72692-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="72692-108">Attribute</span></span>|<span data-ttu-id="72692-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72692-109">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="72692-110">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="72692-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="72692-111">Specifica l'URL in cui il runtime è in grado di trovare la versione specificata dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="72692-111">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="72692-112">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="72692-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="72692-113">Specifica la versione dell'assembly a cui si applica la codebase.</span><span class="sxs-lookup"><span data-stu-id="72692-113">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="72692-114">Il formato di un numero di versione dell'assembly è *Major. minor. Build. Revision*.</span><span class="sxs-lookup"><span data-stu-id="72692-114">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="72692-115">Attributo Version</span><span class="sxs-lookup"><span data-stu-id="72692-115">version Attribute</span></span>

|<span data-ttu-id="72692-116">Valore</span><span class="sxs-lookup"><span data-stu-id="72692-116">Value</span></span>|<span data-ttu-id="72692-117">Description</span><span class="sxs-lookup"><span data-stu-id="72692-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="72692-118">I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="72692-118">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="72692-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="72692-119">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="72692-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="72692-120">Child Elements</span></span>

<span data-ttu-id="72692-121">No.</span><span class="sxs-lookup"><span data-stu-id="72692-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="72692-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="72692-122">Parent Elements</span></span>

|<span data-ttu-id="72692-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="72692-123">Element</span></span>|<span data-ttu-id="72692-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72692-124">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="72692-125">Definisce una raccolta di provider di compilazione utilizzati per compilare file di risorse personalizzati.</span><span class="sxs-lookup"><span data-stu-id="72692-125">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="72692-126">Possono essere presenti più provider di compilazione.</span><span class="sxs-lookup"><span data-stu-id="72692-126">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="72692-127">Configura tutte le impostazioni di compilazione utilizzate da ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="72692-127">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="72692-128">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72692-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="72692-129">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="72692-129">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="72692-130">Commenti</span><span class="sxs-lookup"><span data-stu-id="72692-130">Remarks</span></span>

<span data-ttu-id="72692-131">Affinché il runtime usi l' **\<codeBase>** impostazione in un file di configurazione del computer o in un file dei criteri editore, il file deve anche reindirizzare la versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="72692-131">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="72692-132">I file di configurazione dell'applicazione possono avere un'impostazione codebase senza reindirizzamento della versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="72692-132">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="72692-133">Dopo aver determinato quale versione dell'assembly utilizzare, il runtime applica l'impostazione codebase dal file che determina la versione.</span><span class="sxs-lookup"><span data-stu-id="72692-133">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="72692-134">Se non è indicata alcuna codebase, il runtime esegue il probe per l'assembly nel modo consueto.</span><span class="sxs-lookup"><span data-stu-id="72692-134">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="72692-135">Se l'assembly ha un nome sicuro, l'impostazione codebase può trovarsi in qualsiasi punto della rete Intranet locale o Internet.</span><span class="sxs-lookup"><span data-stu-id="72692-135">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="72692-136">Se l'assembly è un assembly privato, l'impostazione codebase deve essere un percorso relativo alla directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="72692-136">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="72692-137">Per gli assembly senza nome sicuro, la versione viene ignorata e il caricatore usa il primo aspetto di \<codebase> all'interno di \<dependentAssembly> .</span><span class="sxs-lookup"><span data-stu-id="72692-137">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="72692-138">Se nel file di configurazione dell'applicazione è presente una voce che reindirizza il binding a un altro assembly, il reindirizzamento avrà la precedenza anche se la versione dell'assembly non corrisponde alla richiesta di associazione.</span><span class="sxs-lookup"><span data-stu-id="72692-138">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="72692-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="72692-139">Example</span></span>

<span data-ttu-id="72692-140">Nell'esempio seguente viene illustrato come specificare la posizione in cui il runtime può trovare un assembly.</span><span class="sxs-lookup"><span data-stu-id="72692-140">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="72692-141">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="72692-141">See also</span></span>

- [<span data-ttu-id="72692-142">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="72692-142">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="72692-143">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="72692-143">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="72692-144">Specificare la posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="72692-144">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="72692-145">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="72692-145">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
