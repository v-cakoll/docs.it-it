---
title: 'Procedura: creare criteri editore'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 608918828bf72369a1bd48e2391e2423078e9df0
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846840"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="1bf05-102">Procedura: creare criteri editore</span><span class="sxs-lookup"><span data-stu-id="1bf05-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="1bf05-103">I fornitori di assembly possono dichiarare che le applicazioni devono usare una versione più recente di un assembly includendo un file dei criteri editore con l'assembly aggiornato.</span><span class="sxs-lookup"><span data-stu-id="1bf05-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="1bf05-104">Il file dei criteri editore specifica il reindirizzamento degli assembly e le impostazioni di base del codice e usa lo stesso formato di un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1bf05-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="1bf05-105">Il file dei criteri editore viene compilato in un assembly e inserito nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="1bf05-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="1bf05-106">Per la creazione di un criterio editore sono necessari tre passaggi:</span><span class="sxs-lookup"><span data-stu-id="1bf05-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="1bf05-107">Creazione di un file dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="1bf05-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="1bf05-108">Creare un assembly dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="1bf05-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="1bf05-109">Aggiungere l'assembly dei criteri editore al Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="1bf05-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="1bf05-110">Lo schema per i criteri editore è descritto in [Reindirizzamento delle versioni di assembly](redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="1bf05-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="1bf05-111">Nell'esempio seguente viene illustrato un file dei criteri dell'editore che reindirizza una versione di `myAssembly` a un'altra.</span><span class="sxs-lookup"><span data-stu-id="1bf05-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

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

<span data-ttu-id="1bf05-112">Per informazioni su come specificare una base di codice, vedere [specifica della posizione di un assembly](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="1bf05-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="1bf05-113">Creazione dell'assembly dei criteri editore</span><span class="sxs-lookup"><span data-stu-id="1bf05-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="1bf05-114">Usare [assembly linker (al. exe)](../tools/al-exe-assembly-linker.md) per creare l'assembly dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="1bf05-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="1bf05-115">Per creare un assembly dei criteri editore</span><span class="sxs-lookup"><span data-stu-id="1bf05-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="1bf05-116">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1bf05-116">Type the following command at the command prompt:</span></span>

<span data-ttu-id="1bf05-117">**al/link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/Platform:** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="1bf05-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>

<span data-ttu-id="1bf05-118">In questo comando:</span><span class="sxs-lookup"><span data-stu-id="1bf05-118">In this command:</span></span>

- <span data-ttu-id="1bf05-119">L'argomento *publisherPolicyFile* è il nome del file dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="1bf05-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="1bf05-120">L'argomento *publisherPolicyAssemblyFile* è il nome dell'assembly dei criteri editore risultante da questo comando.</span><span class="sxs-lookup"><span data-stu-id="1bf05-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="1bf05-121">Il nome del file di assembly deve avere il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="1bf05-121">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="1bf05-122">**politica.**</span><span class="sxs-lookup"><span data-stu-id="1bf05-122">**policy.**</span></span> <span data-ttu-id="1bf05-123">*majorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="1bf05-123">*majorNumber* **.**</span></span> <span data-ttu-id="1bf05-124">*minorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="1bf05-124">*minorNumber* **.**</span></span> <span data-ttu-id="1bf05-125">*MainAssemblyName* **. dll**</span><span class="sxs-lookup"><span data-stu-id="1bf05-125">*mainAssemblyName* **.dll**</span></span>

- <span data-ttu-id="1bf05-126">L'argomento *keyPairFile* è il nome del file che contiene la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="1bf05-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="1bf05-127">È necessario firmare l'assembly e l'assembly dei criteri editore con la stessa coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="1bf05-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="1bf05-128">L'argomento *processorArchitecture* identifica la piattaforma di destinazione di un assembly specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="1bf05-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1bf05-129">La possibilità di definire come destinazione un'architettura di processore specifica è disponibile a partire da .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="1bf05-129">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="1bf05-130">La possibilità di definire come destinazione un'architettura di processore specifica è disponibile a partire da .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="1bf05-130">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span> <span data-ttu-id="1bf05-131">Il comando seguente crea un assembly dei criteri editore denominato `policy.1.0.myAssembly` da un file di criteri editore denominato `pub.config`, assegna un nome sicuro all'assembly utilizzando la coppia di chiavi nel file `sgKey.snk` e specifica che l'assembly è destinato al processore x86 architettura.</span><span class="sxs-lookup"><span data-stu-id="1bf05-131">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="1bf05-132">L'assembly dei criteri dell'editore deve corrispondere all'architettura del processore dell'assembly a cui si applica.</span><span class="sxs-lookup"><span data-stu-id="1bf05-132">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="1bf05-133">Pertanto, se l'assembly ha un valore <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> <xref:System.Reflection.ProcessorArchitecture.MSIL>, è necessario creare l'assembly dei criteri dell'editore per tale assembly con `/platform:anycpu`.</span><span class="sxs-lookup"><span data-stu-id="1bf05-133">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="1bf05-134">È necessario fornire un assembly dei criteri di pubblicazione separato per ogni assembly specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="1bf05-134">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="1bf05-135">Una conseguenza di questa regola è che, per modificare l'architettura del processore per un assembly, è necessario modificare il componente principale o secondario del numero di versione, in modo che sia possibile fornire un nuovo assembly dei criteri editore con l'architettura del processore corretta.</span><span class="sxs-lookup"><span data-stu-id="1bf05-135">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="1bf05-136">L'assembly dei criteri di pubblicazione precedente non può servire l'assembly quando l'assembly ha un'architettura del processore diversa.</span><span class="sxs-lookup"><span data-stu-id="1bf05-136">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="1bf05-137">Un'altra conseguenza è che non è possibile usare il linker versione 2,0 per creare un assembly dei criteri editore per un assembly compilato usando versioni precedenti del .NET Framework, perché specifica sempre l'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="1bf05-137">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="1bf05-138">Aggiunta dell'assembly dei criteri editore alla Global assembly cache</span><span class="sxs-lookup"><span data-stu-id="1bf05-138">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="1bf05-139">Utilizzare lo [strumento Global Assembly Cache (Gacutil. exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere l'assembly dei criteri editore al Global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="1bf05-139">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="1bf05-140">Per aggiungere l'assembly dei criteri editore al Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="1bf05-140">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="1bf05-141">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1bf05-141">Type the following command at the command prompt:</span></span>

<span data-ttu-id="1bf05-142">**gacutil/I**  *publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="1bf05-142">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>

<span data-ttu-id="1bf05-143">Il comando seguente aggiunge `policy.1.0.myAssembly.dll` al Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="1bf05-143">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="1bf05-144">Non è possibile aggiungere l'assembly dei criteri editore alla Global Assembly Cache a meno che il file dei criteri editore originale si trovi nella stessa directory dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1bf05-144">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bf05-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bf05-145">See also</span></span>

- [<span data-ttu-id="1bf05-146">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="1bf05-146">Programming with Assemblies</span></span>](../../standard/assembly/program.md)
- [<span data-ttu-id="1bf05-147">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="1bf05-147">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="1bf05-148">Configurazione di app tramite file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bf05-148">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="1bf05-149">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="1bf05-149">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="1bf05-150">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="1bf05-150">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="1bf05-151">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="1bf05-151">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
