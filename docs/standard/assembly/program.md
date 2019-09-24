---
title: Programma con assembly
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03babe701b46eab54a76094c4728af80e6d9911e
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70973138"
---
# <a name="program-with-assemblies"></a><span data-ttu-id="a1a08-102">Programma con assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-102">Program with assemblies</span></span>
<span data-ttu-id="a1a08-103">Gli assembly sono i blocchi costitutivi di .NET Framework. Costituiscono la base per la distribuzione, il controllo della versione, il riutilizzo, la definizione dell'ambito di attivazione e le autorizzazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="a1a08-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="a1a08-104">Un assembly offre a Common Language Runtime le informazioni necessarie per il riconoscimento delle implementazioni di tipi.</span><span class="sxs-lookup"><span data-stu-id="a1a08-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="a1a08-105">È una raccolta di tipi e risorse creati per essere usati insieme e per formare un'unità logica di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a1a08-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="a1a08-106">Per il runtime, un tipo non esiste all'esterno del contesto di un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="a1a08-107">Questa sezione descrive come creare moduli, come creare assembly da moduli, come creare una coppia di chiavi e firmare un assembly con un nome sicuro e infine come installare un assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a1a08-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="a1a08-108">Questa sezione descrive anche come usare [MSIL Disassembler (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) per visualizzare informazioni sul manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1a08-109">A partire da .NET Framework versione 2.0 il runtime non caricherà un assembly compilato con una versione di .NET Framework con numero di versione superiore a quello del runtime attualmente caricato.</span><span class="sxs-lookup"><span data-stu-id="a1a08-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="a1a08-110">Questo vale per la combinazione dei componenti numero principale e numero secondario del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="a1a08-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1a08-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a1a08-111">In this section</span></span>  
 [<span data-ttu-id="a1a08-112">Creazione di assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-112">Create assemblies</span></span>](create.md)  
 <span data-ttu-id="a1a08-113">Offre una panoramica degli assembly a file singolo e su più file.</span><span class="sxs-lookup"><span data-stu-id="a1a08-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="a1a08-114">Nomi degli assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-114">Assembly names</span></span>](names.md)  
 <span data-ttu-id="a1a08-115">Offre una panoramica dell'assegnazione dei nomi agli assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="a1a08-116">Procedura: Determinare il nome completo di un assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-116">How to: Determine an assembly's fully qualified name</span></span>](find-fully-qualified-name.md)  
 <span data-ttu-id="a1a08-117">Descrive come determinare il nome completo di un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="a1a08-118">Esecuzione di applicazioni Intranet in attendibilità totale</span><span class="sxs-lookup"><span data-stu-id="a1a08-118">Run intranet applications in full trust</span></span>](../../framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="a1a08-119">Descrive come specificare criteri di sicurezza legacy per assembly con attendibilità totale in una condivisione di rete Intranet.</span><span class="sxs-lookup"><span data-stu-id="a1a08-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="a1a08-120">Percorso assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-120">Assembly location</span></span>](location.md)  
 <span data-ttu-id="a1a08-121">Offre una panoramica della posizione in cui si trovano gli assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="a1a08-122">Procedura: Compilare un assembly a file singolo</span><span class="sxs-lookup"><span data-stu-id="a1a08-122">How to: Build a single-file assembly</span></span>](../../framework/app-domains/build-single-file-assembly.md)  
 <span data-ttu-id="a1a08-123">Descrive come creare un assembly su singolo file.</span><span class="sxs-lookup"><span data-stu-id="a1a08-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="a1a08-124">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="a1a08-124">Multifile assemblies</span></span>](../../framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="a1a08-125">Descrive i motivi per la creazione di assembly su più file.</span><span class="sxs-lookup"><span data-stu-id="a1a08-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="a1a08-126">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="a1a08-126">How to: Build a multifile assembly</span></span>](../../framework/app-domains/build-multifile-assembly.md)  
 <span data-ttu-id="a1a08-127">Descrive come creare un assembly su più file.</span><span class="sxs-lookup"><span data-stu-id="a1a08-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="a1a08-128">Impostare gli attributi dell'assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-128">Set assembly attributes</span></span>](set-attributes.md)  
 <span data-ttu-id="a1a08-129">Descrive gli attributi dell'assembly e come impostarli.</span><span class="sxs-lookup"><span data-stu-id="a1a08-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="a1a08-130">Creazione e utilizzo di assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="a1a08-130">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)  
 <span data-ttu-id="a1a08-131">Descrive come e perché aggiungere un nome sicuro a un assembly e include procedure.</span><span class="sxs-lookup"><span data-stu-id="a1a08-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="a1a08-132">Ritardare la firma di un assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-132">Delay-sign an assembly</span></span>](delay-sign.md)  
 <span data-ttu-id="a1a08-133">Descrive come ritardare la firma di un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="a1a08-134">Usare gli assembly e i Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a1a08-134">Work with assemblies and the global assembly cache</span></span>](../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="a1a08-135">Descrive come e perché aggiungere assembly alla Global Assembly Cache e include argomenti relativi a procedure.</span><span class="sxs-lookup"><span data-stu-id="a1a08-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="a1a08-136">Procedura: Visualizza contenuto assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-136">How to: View assembly contents</span></span>](view-contents.md)  
 <span data-ttu-id="a1a08-137">Descrive come usare MSIL Disassembler (Ildasm.exe) per visualizzare il contenuto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="a1a08-138">Invio del tipo nell'Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a1a08-138">Type forwarding in the common language runtime</span></span>](type-forwarding.md)  
 <span data-ttu-id="a1a08-139">Descrive come usare l'inoltro del tipo per spostare un tipo in un assembly diverso senza compromettere il funzionamento delle applicazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="a1a08-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a1a08-140">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="a1a08-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="a1a08-141">Classe di .NET Framework che rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a1a08-142">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a1a08-142">Related sections</span></span>  
 [<span data-ttu-id="a1a08-143">Procedura: Ottenere informazioni sul tipo e sui membri da un assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-143">How to: Obtain type and member information from an assembly</span></span>](../../framework/reflection-and-codedom/get-type-member-information.md)  
 <span data-ttu-id="a1a08-144">Descrive come ottenere a livello di codice il tipo e altre informazioni relative a un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 [<span data-ttu-id="a1a08-145">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="a1a08-145">Assemblies in .NET</span></span>](index.md)  
 <span data-ttu-id="a1a08-146">Offre una panoramica concettuale sugli assembly Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a1a08-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="a1a08-147">Controllo delle versioni degli assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-147">Assembly versioning</span></span>](versioning.md)  
 <span data-ttu-id="a1a08-148">Offre una panoramica dell'associazione di assembly e degli attributi <xref:System.Reflection.AssemblyVersionAttribute> e <xref:System.Reflection.AssemblyInformationalVersionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a1a08-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="a1a08-149">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="a1a08-149">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="a1a08-150">Descrive come il runtime determina l'assembly da usare per eseguire una richiesta di associazione.</span><span class="sxs-lookup"><span data-stu-id="a1a08-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 <span data-ttu-id="a1a08-151">[Reflection](../../framework/reflection-and-codedom/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="a1a08-151">[Reflection](../../framework/reflection-and-codedom/reflection.md) </span></span>  
 <span data-ttu-id="a1a08-152">Descrive come usare la classe **Reflection** per ottenere informazioni su un assembly.</span><span class="sxs-lookup"><span data-stu-id="a1a08-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>