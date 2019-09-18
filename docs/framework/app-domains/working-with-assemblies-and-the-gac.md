---
title: Utilizzo di assembly e della Global Assembly Cache
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0331e0ad30743d5f0bba125e8e61e636e1c2a5be
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053031"
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a><span data-ttu-id="a3bd1-102">Utilizzo di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a3bd1-102">Working with Assemblies and the Global Assembly Cache</span></span>

<span data-ttu-id="a3bd1-103">Se si vuole condividere un assembly tra diverse applicazioni, è possibile installarlo nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-103">If you intend to share an assembly among several applications, you can install it into the global assembly cache.</span></span> <span data-ttu-id="a3bd1-104">Tale cache di codice a livello di computer si trova su ogni computer in cui è installato Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-104">Each computer where the common language runtime is installed has this machine-wide code cache.</span></span> <span data-ttu-id="a3bd1-105">La Global Assembly Cache memorizza gli assembly specificamente designati per essere condivisi da più applicazioni sul computer.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-105">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span> <span data-ttu-id="a3bd1-106">L'assembly deve avere un nome sicuro per essere installato nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-106">An assembly must have a strong name to be installed in the global assembly cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3bd1-107">Gli assembly nella Global Assembly Cache devono avere lo stesso nome di assembly e lo stesso nome di file, ad esclusione dell'estensione del nome del file.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-107">Assemblies placed in the global assembly cache must have the same assembly name and file name (not including the file name extension).</span></span> <span data-ttu-id="a3bd1-108">Ad esempio, un assembly con il nome assembly myAssembly deve avere un nome di file myAssembly.exe o myAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-108">For example, an assembly with the assembly name of myAssembly must have a file name of either myAssembly.exe or myAssembly.dll.</span></span>  
  
<span data-ttu-id="a3bd1-109">Per condividere gli assembly, installarli nella Global Assembly Cache solo quando è necessario.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-109">You should share assemblies by installing them into the global assembly cache only when necessary.</span></span> <span data-ttu-id="a3bd1-110">Come regola generale, mantenere le dipendenze degli assembly private e individuare gli assembly nella directory dell'applicazione, a meno che la condivisione di un assembly non venga richiesta in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-110">As a general guideline, keep assembly dependencies private and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="a3bd1-111">Non è necessario installare gli assembly nella Global Assembly Cache per renderli accessibili al codice non gestito o all'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-111">In addition, you do not have to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
<span data-ttu-id="a3bd1-112">Esistono diverse ragioni per cui installare un assembly nella Global Assembly Cache:</span><span class="sxs-lookup"><span data-stu-id="a3bd1-112">There are several reasons why you might want to install an assembly into the global assembly cache:</span></span>  
  
- <span data-ttu-id="a3bd1-113">Percorso condiviso.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-113">Shared location.</span></span>  
  
     <span data-ttu-id="a3bd1-114">Gli assembly che devono essere usati dalle applicazioni possono essere inseriti nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-114">Assemblies that should be used by applications can be put in the global assembly cache.</span></span> <span data-ttu-id="a3bd1-115">Ad esempio, se tutte le applicazioni devono usare un assembly nella Global Assembly Cache, è possibile aggiungere un'istruzione di criteri di versione al file Machine.config che reindirizza i riferimenti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-115">For example, if all applications should use an assembly located in the global assembly cache, a version policy statement can be added to the Machine.config file that redirects references to the assembly.</span></span>  
  
- <span data-ttu-id="a3bd1-116">Sicurezza dei file.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-116">File security.</span></span>  
  
     <span data-ttu-id="a3bd1-117">Gli amministratori spesso proteggono la directory systemroot usando un elenco di controllo di accesso (ACL) per controllare l'accesso in scrittura ed esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-117">Administrators often protect the systemroot directory using an Access Control List (ACL) to control write and execute access.</span></span> <span data-ttu-id="a3bd1-118">Poiché la Global Assembly Cache viene installata nella directory systemroot, eredita l'ACL di tale directory.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-118">Because the global assembly cache is installed in the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="a3bd1-119">È consigliabile che solo gli utenti con privilegi di amministratore siano autorizzati a eliminare file dalla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-119">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
- <span data-ttu-id="a3bd1-120">Controllo delle versioni side-by-side.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-120">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="a3bd1-121">Nella Global Assembly Cache possono essere gestite più copie di assembly con lo stesso nome ma con informazioni di versione diverse.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-121">Multiple copies of assemblies with the same name but different version information can be maintained in the global assembly cache.</span></span>  
  
- <span data-ttu-id="a3bd1-122">Altri percorsi di ricerca.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-122">Additional search location.</span></span>  
  
     <span data-ttu-id="a3bd1-123">Common language runtime cerca nella Global Assembly Cache un assembly che corrisponda alla richiesta di assembly prima di effettuare l'esecuzione del probe o usare le informazioni della base di codici in un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-123">The common language runtime checks the global assembly cache for an assembly that matches the assembly request before probing or using the codebase information in a configuration file.</span></span>  
  
 <span data-ttu-id="a3bd1-124">Si noti che esistono scenari in cui si sceglie in modo esplicito di non installare un assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-124">Note that there are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="a3bd1-125">Se si inserisce uno degli assembly che costituiscono un'applicazione nella Global Assembly Cache, non sarà più possibile replicare o installare l'applicazione usando il comando XCOPY per copiare la directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-125">If you place one of the assemblies that make up an application into the global assembly cache, you can no longer replicate or install the application by using XCOPY to copy the application directory.</span></span> <span data-ttu-id="a3bd1-126">In questo caso è necessario anche spostare l'assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-126">In this case, you must also move the assembly into the global assembly cache.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3bd1-127">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="a3bd1-127">In This Section</span></span>  
[<span data-ttu-id="a3bd1-128">Procedura: Installare un assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a3bd1-128">How to: Install an Assembly into the Global Assembly Cache</span></span>](install-assembly-into-gac.md)  
<span data-ttu-id="a3bd1-129">Vengono descritte le modalità di installazione di un assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-129">Describes the ways to install an assembly into the global assembly cache.</span></span>  
  
[<span data-ttu-id="a3bd1-130">Procedura: Visualizzare il contenuto della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a3bd1-130">How to: View the Contents of the Global Assembly Cache</span></span>](how-to-view-the-contents-of-the-gac.md)  
<span data-ttu-id="a3bd1-131">Illustra come usare [lo strumento Global Assembly Cache (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per visualizzare i contenuti della Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-131">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
[<span data-ttu-id="a3bd1-132">Procedura: Rimuovere un assembly dalla Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a3bd1-132">How to: Remove an Assembly from the Global Assembly Cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)  
<span data-ttu-id="a3bd1-133">Illustra come usare [lo strumento Global Assembly Cache (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per rimuovere un assembly dalla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-133">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to remove an assembly from the global assembly cache.</span></span>  
  
[<span data-ttu-id="a3bd1-134">Uso dei componenti serviti con la Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a3bd1-134">Using Serviced Components with the Global Assembly Cache</span></span>](use-serviced-components-with-the-gac.md)  
<span data-ttu-id="a3bd1-135">È consigliabile inserire nella Global Assembly Cache i componenti serviti (componenti COM+ di codice gestito).</span><span class="sxs-lookup"><span data-stu-id="a3bd1-135">Explains why serviced components (managed COM+ components) should be placed in the global assembly cache.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a3bd1-136">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a3bd1-136">Related Sections</span></span>  

[<span data-ttu-id="a3bd1-137">Creazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="a3bd1-137">Creating Assemblies</span></span>](../../standard/assembly/create.md)  
<span data-ttu-id="a3bd1-138">Offre una panoramica della creazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-138">Provides an overview of creating assemblies.</span></span>  
  
[<span data-ttu-id="a3bd1-139">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a3bd1-139">Global Assembly Cache</span></span>](gac.md)  
<span data-ttu-id="a3bd1-140">Descrive la Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-140">Describes the global assembly cache.</span></span>  
  
[<span data-ttu-id="a3bd1-141">Procedura: Visualizzare il contenuto degli assembly</span><span class="sxs-lookup"><span data-stu-id="a3bd1-141">How to: View Assembly Contents</span></span>](../../standard/assembly/view-contents.md)  
<span data-ttu-id="a3bd1-142">Illustra come usare [Ildasm.exe (Disassembler IL)](../tools/ildasm-exe-il-disassembler.md) per visualizzare le informazioni di Microsoft Intermediate Language (MSIL) in un assembly.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-142">Explains how to use the [Ildasm.exe (IL Disassembler)](../tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in an assembly.</span></span>  
  
[<span data-ttu-id="a3bd1-143">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="a3bd1-143">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)  
<span data-ttu-id="a3bd1-144">Descrive in che modo Common Language Runtime individua e carica gli assembly che costituiscono l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-144">Describes how the common language runtime locates and loads the assemblies that make up your application.</span></span>  
  
[<span data-ttu-id="a3bd1-145">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="a3bd1-145">Programming with Assemblies</span></span>](../../standard/assembly/program.md)  
<span data-ttu-id="a3bd1-146">Descrive gli assembly, i blocchi predefiniti delle applicazioni gestite.</span><span class="sxs-lookup"><span data-stu-id="a3bd1-146">Describes assemblies, the building blocks of managed applications.</span></span>
