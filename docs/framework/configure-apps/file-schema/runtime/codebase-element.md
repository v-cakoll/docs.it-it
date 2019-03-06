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
ms.openlocfilehash: b5825efcc613689e73fb56b6695fe7c75ff09136
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356611"
---
# <a name="codebase-element"></a><span data-ttu-id="7b559-102">\<codeBase > elemento</span><span class="sxs-lookup"><span data-stu-id="7b559-102">\<codeBase> Element</span></span>

<span data-ttu-id="7b559-103">Specifica in cui common language runtime può trovare un assembly.</span><span class="sxs-lookup"><span data-stu-id="7b559-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="7b559-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span><span class="sxs-lookup"><span data-stu-id="7b559-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span></span>

## <a name="syntax"></a><span data-ttu-id="7b559-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b559-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7b559-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7b559-106">Attributes and Elements</span></span>

<span data-ttu-id="7b559-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7b559-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7b559-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="7b559-108">Attributes</span></span>

|<span data-ttu-id="7b559-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="7b559-109">Attribute</span></span>|<span data-ttu-id="7b559-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b559-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="7b559-111">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7b559-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="7b559-112">Specifica l'URL in cui il runtime può trovare la versione dell'assembly specificata.</span><span class="sxs-lookup"><span data-stu-id="7b559-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="7b559-113">Attributo obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7b559-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7b559-114">Specifica la versione dell'assembly che viene applicata la codebase.</span><span class="sxs-lookup"><span data-stu-id="7b559-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="7b559-115">Il formato di un numero di versione assembly *revisione*.</span><span class="sxs-lookup"><span data-stu-id="7b559-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="7b559-116">Attributo di versione</span><span class="sxs-lookup"><span data-stu-id="7b559-116">version Attribute</span></span>

|<span data-ttu-id="7b559-117">Valore</span><span class="sxs-lookup"><span data-stu-id="7b559-117">Value</span></span>|<span data-ttu-id="7b559-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b559-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="7b559-119">I valori validi per ogni parte del numero di versione sono compresi tra 0 e 65535.</span><span class="sxs-lookup"><span data-stu-id="7b559-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="7b559-120">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="7b559-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7b559-121">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7b559-121">Child Elements</span></span>

<span data-ttu-id="7b559-122">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7b559-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7b559-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7b559-123">Parent Elements</span></span>

|<span data-ttu-id="7b559-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7b559-124">Element</span></span>|<span data-ttu-id="7b559-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b559-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="7b559-126">Definisce una raccolta di provider di compilazione utilizzati per compilare file di risorse personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7b559-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="7b559-127">Possono essere presenti più provider di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7b559-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="7b559-128">Consente di configurare tutte le impostazioni di compilazione usato da ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7b559-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="7b559-129">Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b559-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="7b559-130">Consente di specificare l'elemento radice per la sezione di configurazione ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7b559-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7b559-131">Note</span><span class="sxs-lookup"><span data-stu-id="7b559-131">Remarks</span></span>

<span data-ttu-id="7b559-132">Per il runtime utilizzare la  **\<codeBase >** impostazione in un file di configurazione di computer o i file dei criteri editore, il file anche necessario reindirizzare la versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7b559-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="7b559-133">File di configurazione dell'applicazione possono avere un'impostazione di base di codice senza eseguire il reindirizzamento alla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7b559-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="7b559-134">Dopo aver determinato la versione di assembly da usare, il runtime si applica l'impostazione di base di codice dal file che determina la versione.</span><span class="sxs-lookup"><span data-stu-id="7b559-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="7b559-135">Se non viene specificata alcuna codebase, il runtime esegue il probe per l'assembly nel modo consueto.</span><span class="sxs-lookup"><span data-stu-id="7b559-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="7b559-136">Se l'assembly ha un nome sicuro, la codebase può trovarsi in un punto qualsiasi nella rete intranet locale o in Internet.</span><span class="sxs-lookup"><span data-stu-id="7b559-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="7b559-137">Se l'assembly è un assembly privato, l'impostazione di base di codice deve essere un percorso relativo alla directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7b559-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="7b559-138">Per gli assembly senza un nome sicuro, la versione viene ignorata e il caricatore Usa la prima occorrenza di \<codebase > all'interno di \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="7b559-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="7b559-139">Se è presente una voce nel file di configurazione dell'applicazione che reindirizza l'associazione a un altro assembly, il reindirizzamento avrà la precedenza anche se la versione dell'assembly non corrisponde alla richiesta di associazione.</span><span class="sxs-lookup"><span data-stu-id="7b559-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="7b559-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b559-140">Example</span></span>

<span data-ttu-id="7b559-141">Nell'esempio seguente viene illustrato come specificare dove il runtime può trovare un assembly.</span><span class="sxs-lookup"><span data-stu-id="7b559-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7b559-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b559-142">See also</span></span>

- [<span data-ttu-id="7b559-143">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="7b559-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7b559-144">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="7b559-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7b559-145">Specifica della posizione di un assembly</span><span class="sxs-lookup"><span data-stu-id="7b559-145">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [<span data-ttu-id="7b559-146">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="7b559-146">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
