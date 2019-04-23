---
title: 'Procedura: Creare criteri editore'
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: ce2df9d4cea601652ebde2032758137b01faacdc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344663"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="94f76-102">Procedura: Creare criteri editore</span><span class="sxs-lookup"><span data-stu-id="94f76-102">How to: Create a Publisher Policy</span></span>
<span data-ttu-id="94f76-103">I fornitori di assembly possono indicare che le applicazioni devono utilizzare una versione più recente di un assembly includendo un file dei criteri editore con l'assembly aggiornato.</span><span class="sxs-lookup"><span data-stu-id="94f76-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="94f76-104">File dei criteri editore specifica il reindirizzamento di assembly e le impostazioni della codebase e Usa lo stesso formato di un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="94f76-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="94f76-105">File dei criteri editore viene compilato in un assembly e inserito nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="94f76-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="94f76-106">Esistono tre passaggi coinvolti nella creazione di un criterio server di pubblicazione:</span><span class="sxs-lookup"><span data-stu-id="94f76-106">There are three steps involved in creating a publisher policy:</span></span>  
  
1. <span data-ttu-id="94f76-107">Creare un file dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="94f76-107">Create a publisher policy file.</span></span>  
  
2. <span data-ttu-id="94f76-108">Creare un assembly dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="94f76-108">Create a publisher policy assembly.</span></span>  
  
3. <span data-ttu-id="94f76-109">Aggiungere l'assembly dei criteri editore nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="94f76-109">Add the publisher policy assembly to the global assembly cache.</span></span>  
  
 <span data-ttu-id="94f76-110">Lo schema dei criteri dell'editore è descritto nella [reindirizzamento delle versioni degli Assembly](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="94f76-110">The schema for publisher policy is described in [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span></span> <span data-ttu-id="94f76-111">L'esempio seguente illustra un server di pubblicazione file dei criteri che reindirizza una versione `myAssembly` a altro.</span><span class="sxs-lookup"><span data-stu-id="94f76-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>  
  
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
  
 <span data-ttu-id="94f76-112">Per informazioni su come specificare una base di codice, vedere [che specifica la posizione dell'Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="94f76-112">To learn how to specify a code base, see [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  
  
## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="94f76-113">Creazione di Assembly dei criteri editore</span><span class="sxs-lookup"><span data-stu-id="94f76-113">Creating the Publisher Policy Assembly</span></span>  
 <span data-ttu-id="94f76-114">Usare la [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) per creare l'assembly del criterio server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="94f76-114">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>  
  
#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="94f76-115">Per creare un assembly dei criteri editore</span><span class="sxs-lookup"><span data-stu-id="94f76-115">To create a publisher policy assembly</span></span>  
  
1. <span data-ttu-id="94f76-116">Digitare il comando seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="94f76-116">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="94f76-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:**  *keyPairFile* **/platform:** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="94f76-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>  
  
     <span data-ttu-id="94f76-118">In questo comando:</span><span class="sxs-lookup"><span data-stu-id="94f76-118">In this command:</span></span>  
  
    -   <span data-ttu-id="94f76-119">Il *publisherPolicyFile* argomento è il nome del file dei criteri editore.</span><span class="sxs-lookup"><span data-stu-id="94f76-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>  
  
    -   <span data-ttu-id="94f76-120">Il *publisherPolicyAssemblyFile* argomento è il nome dell'assembly dei criteri editore risultante da questo comando.</span><span class="sxs-lookup"><span data-stu-id="94f76-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="94f76-121">Nome file dell'assembly deve seguire il formato:</span><span class="sxs-lookup"><span data-stu-id="94f76-121">The assembly file name must follow the format:</span></span>  
  
         <span data-ttu-id="94f76-122">**policy.**</span><span class="sxs-lookup"><span data-stu-id="94f76-122">**policy.**</span></span> <span data-ttu-id="94f76-123">*majorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="94f76-123">*majorNumber* **.**</span></span> <span data-ttu-id="94f76-124">*minorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="94f76-124">*minorNumber* **.**</span></span> <span data-ttu-id="94f76-125">*mainAssemblyName* **.dll**</span><span class="sxs-lookup"><span data-stu-id="94f76-125">*mainAssemblyName* **.dll**</span></span>  
  
    -   <span data-ttu-id="94f76-126">Il *keyPairFile* argomento è il nome del file contenente la coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="94f76-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="94f76-127">È necessario firmare l'assembly e assembly dei criteri editore con la stessa coppia di chiavi.</span><span class="sxs-lookup"><span data-stu-id="94f76-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>  
  
    -   <span data-ttu-id="94f76-128">Il *processorArchitecture* argomento identifica la piattaforma di destinazione da un assembly specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="94f76-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="94f76-129">La possibilità di un'architettura di processore specifica di destinazione è le novità di .NET Framework versione 2.0.</span><span class="sxs-lookup"><span data-stu-id="94f76-129">The ability to target a specific processor architecture is new in the .NET Framework version 2.0.</span></span>  
  
     <span data-ttu-id="94f76-130">Il comando seguente crea un assembly dei criteri editore chiamato `policy.1.0.myAssembly` chiamato da un file dei criteri editore `pub.config`, assegna un nome sicuro all'assembly usando la coppia di chiavi nel `sgKey.snk` file e specifica che l'assembly abbia come destinazione x86 architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="94f76-130">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     <span data-ttu-id="94f76-131">L'assembly dei criteri editore deve corrispondere all'architettura di processore dell'assembly che si applica a.</span><span class="sxs-lookup"><span data-stu-id="94f76-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="94f76-132">Di conseguenza, se l'assembly ha un <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> valore del <xref:System.Reflection.ProcessorArchitecture.MSIL>, l'assembly dei criteri editore per tale assembly deve essere creato con `/platform:anycpu`.</span><span class="sxs-lookup"><span data-stu-id="94f76-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="94f76-133">È necessario fornire un oggetto separato assembly dei criteri editore per ogni assembly specifico del processore.</span><span class="sxs-lookup"><span data-stu-id="94f76-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>  
  
     <span data-ttu-id="94f76-134">Una conseguenza di questa regola è che, per modificare l'architettura del processore per un assembly, è necessario modificare il componente principale o secondario del numero di versione, in modo che è possibile fornire un nuovo assembly dei criteri editore con l'architettura del processore corretta.</span><span class="sxs-lookup"><span data-stu-id="94f76-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="94f76-135">Il vecchio assembly dei criteri editore non è in grado di soddisfare l'assembly dopo che l'assembly ha un'architettura di processore differente.</span><span class="sxs-lookup"><span data-stu-id="94f76-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>  
  
     <span data-ttu-id="94f76-136">Un altro motivo, il linker versione 2.0 non può essere utilizzato per creare un assembly dei criteri editore per un assembly compilato con le versioni precedenti di .NET Framework, poiché viene specificata l'architettura del processore.</span><span class="sxs-lookup"><span data-stu-id="94f76-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="94f76-137">Aggiunta di Assembly dei criteri editore per Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="94f76-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>  
 <span data-ttu-id="94f76-138">Usare la [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) per aggiungere l'assembly dei criteri editore nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="94f76-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="94f76-139">Per aggiungere l'assembly dei criteri editore nella global assembly cache</span><span class="sxs-lookup"><span data-stu-id="94f76-139">To add the publisher policy assembly to the global assembly cache</span></span>  
  
1. <span data-ttu-id="94f76-140">Digitare il comando seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="94f76-140">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="94f76-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="94f76-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>  
  
     <span data-ttu-id="94f76-142">Il seguente comando aggiunge `policy.1.0.myAssembly.dll` alla global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="94f76-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="94f76-143">Impossibile aggiungere l'assembly dei criteri editore nella global assembly cache, a meno che il file dei criteri editore originale si trova nella stessa directory dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="94f76-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f76-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94f76-144">See also</span></span>

- [<span data-ttu-id="94f76-145">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="94f76-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="94f76-146">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="94f76-146">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="94f76-147">Configurazione delle App usando i file di configurazione</span><span class="sxs-lookup"><span data-stu-id="94f76-147">Configuring Apps by using Configuration Files</span></span>](../../../docs/framework/configure-apps/index.md)
- [<span data-ttu-id="94f76-148">Schema delle impostazioni di runtime</span><span class="sxs-lookup"><span data-stu-id="94f76-148">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="94f76-149">Schema dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="94f76-149">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="94f76-150">Reindirizzamento delle versioni di assembly</span><span class="sxs-lookup"><span data-stu-id="94f76-150">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
