---
title: 'Procedura: creare criteri editore'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 7c36f6126f0d779a43a22fc11e647ba2d3b03a30
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646051"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="ce2b4-102">Procedura: creare criteri editore</span><span class="sxs-lookup"><span data-stu-id="ce2b4-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="ce2b4-103">I fornitori di assembly possono indicare che le applicazioni devono utilizzare una versione più recente di un assembly includendo un file dei criteri editore con l'assembly aggiornato.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="ce2b4-104">Il file dei criteri editore specifica il reindirizzamento dell'assembly e le impostazioni della base di codice e utilizza lo stesso formato di un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="ce2b4-105">Il file dei criteri editore viene compilato in un assembly e inserito nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="ce2b4-106">La creazione di criteri per l'editore prevede tre passaggi:There are three steps involved in creating a publisher policy:</span><span class="sxs-lookup"><span data-stu-id="ce2b4-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="ce2b4-107">Creare un file dei criteri dell'editore.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="ce2b4-108">Creare un assembly dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="ce2b4-109">Aggiungere l'assembly dei criteri editore alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="ce2b4-110">Lo schema per i criteri editore è descritto in [Reindirizzamento delle versioni degli assembly](redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="ce2b4-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="ce2b4-111">Nell'esempio seguente viene illustrato un file `myAssembly` dei criteri editore che reindirizza una versione di a un'altra.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
       <dependentAssembly>
         <assemblyIdentity name="myAssembly"
                           publicKeyToken="32ab4ba45e0a69a1"
                           culture="en-us" />
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->
         <bindingRedirect oldVersion="1.0.0.0"
                          newVersion="2.0.0.0"/>
       </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

<span data-ttu-id="ce2b4-112">Per informazioni su come specificare una base di codice, vedere [Specifica del percorso di un assieme](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="ce2b4-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="ce2b4-113">Creazione dell'assembly dei criteri editore</span><span class="sxs-lookup"><span data-stu-id="ce2b4-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="ce2b4-114">Utilizzare [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) per creare l'assembly dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="ce2b4-115">Per creare un assembly dei criteri editoreTo create a publisher policy assembly</span><span class="sxs-lookup"><span data-stu-id="ce2b4-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="ce2b4-116">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ce2b4-116">Type the following command at the command prompt:</span></span>

```console
al /link:publisherPolicyFile /out:publisherPolicyAssemblyFile /keyfile:keyPairFile /platform:processorArchitecture
```

<span data-ttu-id="ce2b4-117">In questo comando:</span><span class="sxs-lookup"><span data-stu-id="ce2b4-117">In this command:</span></span>

- <span data-ttu-id="ce2b4-118">L'argomento `publisherPolicyFile` è il nome del file dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-118">The `publisherPolicyFile` argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="ce2b4-119">L'argomento `publisherPolicyAssemblyFile` è il nome dell'assembly dei criteri editore risultante da questo comando.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-119">The `publisherPolicyAssemblyFile` argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="ce2b4-120">Il nome del file di assieme deve seguire il formato:</span><span class="sxs-lookup"><span data-stu-id="ce2b4-120">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="ce2b4-121">'policy.majorNumber.minorNumber.mainAssemblyName.dll'</span><span class="sxs-lookup"><span data-stu-id="ce2b4-121">\`policy.majorNumber.minorNumber.mainAssemblyName.dll'</span></span>

- <span data-ttu-id="ce2b4-122">L'argomento `keyPairFile` è il nome del file contenente la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-122">The `keyPairFile` argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="ce2b4-123">È necessario firmare l'assembly e l'assembly dei criteri editore con la stessa coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-123">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="ce2b4-124">L'argomento `processorArchitecture` identifica la piattaforma di destinazione di un assembly specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-124">The `processorArchitecture` argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ce2b4-125">La possibilità di impostare come destinazione un'architettura di processore specifica a partire da .NET Framework 2.0.The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-125">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="ce2b4-126">La possibilità di impostare come destinazione un'architettura di processore specifica a partire da .NET Framework 2.0.The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-126">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="ce2b4-127">Il comando riportato di `policy.1.0.myAssembly` seguito consente di `pub.config`creare un assembly dei criteri editore chiamato `sgKey.snk` da un file dei criteri editore denominato , assegna un nome sicuro all'assembly utilizzando la coppia di chiavi nel file e specifica che l'assembly è destinato all'architettura del processore x86.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-127">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```console
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="ce2b4-128">L'assembly dei criteri editore deve corrispondere all'architettura del processore dell'assembly a cui si applica.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-128">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="ce2b4-129">Pertanto, se l'assembly ha un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valore pari a <xref:System.Reflection.ProcessorArchitecture.MSIL>, `/platform:anycpu`l'assembly dei criteri editore per tale assembly deve essere creato con .</span><span class="sxs-lookup"><span data-stu-id="ce2b4-129">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="ce2b4-130">È necessario fornire un assembly dei criteri editore separato per ogni assembly specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-130">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="ce2b4-131">Una conseguenza di questa regola è che per modificare l'architettura del processore per un assembly, è necessario modificare il componente principale o secondario del numero di versione, in modo che sia possibile fornire un nuovo assembly dei criteri editore con l'architettura del processore corretta.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-131">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="ce2b4-132">L'assembly dei criteri editore precedente non può eseguire il servizio dell'assembly quando l'assembly ha un'architettura di processore diversa.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-132">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="ce2b4-133">Un'altra conseguenza è che il linker della versione 2.0 non può essere utilizzato per creare un assembly dei criteri editore per un assembly compilato utilizzando versioni precedenti di .NET Framework, poiché specifica sempre l'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-133">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="ce2b4-134">Aggiunta dell'assembly dei criteri editore alla Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="ce2b4-134">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="ce2b4-135">Utilizzare lo [strumento Global Assembly Cache (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere l'assembly dei criteri editore alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-135">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="ce2b4-136">Per aggiungere l'assembly dei criteri editore alla Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="ce2b4-136">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="ce2b4-137">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ce2b4-137">Type the following command at the command prompt:</span></span>

```console
gacutil /i publisherPolicyAssemblyFile
```

<span data-ttu-id="ce2b4-138">Il comando `policy.1.0.myAssembly.dll` seguente aggiunge alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-138">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```console
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="ce2b4-139">L'assembly dei criteri editore non può essere aggiunto alla `/link` Global Assembly Cache a meno che il file dei criteri editore originale specificato nell'argomento non si trovi nella stessa directory dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-139">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file specified in the `/link` argument is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce2b4-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce2b4-140">See also</span></span>

- [<span data-ttu-id="ce2b4-141">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="ce2b4-141">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="ce2b4-142">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="ce2b4-142">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="ce2b4-143">Configurazione delle app tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ce2b4-143">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="ce2b4-144">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="ce2b4-144">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="ce2b4-145">Schema del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="ce2b4-145">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="ce2b4-146">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="ce2b4-146">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
