---
title: Programmazione con gli assembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46cc7d1be867ff94ca25d0d6ffaaf46a6dc9514b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="programming-with-assemblies"></a><span data-ttu-id="25256-102">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="25256-102">Programming with Assemblies</span></span>
<span data-ttu-id="25256-103">Gli assembly sono i blocchi costitutivi di .NET Framework. Costituiscono la base per la distribuzione, il controllo della versione, il riutilizzo, la definizione dell'ambito di attivazione e le autorizzazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="25256-103">Assemblies are the building blocks of the .NET Framework; they form the fundamental unit of deployment, version control, reuse, activation scoping, and security permissions.</span></span> <span data-ttu-id="25256-104">Un assembly offre a Common Language Runtime le informazioni necessarie per il riconoscimento delle implementazioni di tipi.</span><span class="sxs-lookup"><span data-stu-id="25256-104">An assembly provides the common language runtime with the information it needs to be aware of type implementations.</span></span> <span data-ttu-id="25256-105">È una raccolta di tipi e risorse creati per essere usati insieme e per formare un'unità logica di funzionalità.</span><span class="sxs-lookup"><span data-stu-id="25256-105">It is a collection of types and resources that are built to work together and form a logical unit of functionality.</span></span> <span data-ttu-id="25256-106">Per il runtime, un tipo non esiste all'esterno del contesto di un assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-106">To the runtime, a type does not exist outside the context of an assembly.</span></span>  
  
 <span data-ttu-id="25256-107">Questa sezione descrive come creare moduli, come creare assembly da moduli, come creare una coppia di chiavi e firmare un assembly con un nome sicuro e infine come installare un assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="25256-107">This section describes how to create modules, create assemblies from modules, create a key pair and sign an assembly with a strong name, and install an assembly into the global assembly cache.</span></span> <span data-ttu-id="25256-108">Questa sezione descrive anche come usare [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per visualizzare informazioni sul manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-108">In addition, this section describes how to use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view assembly manifest information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25256-109">A partire da .NET Framework versione 2.0 il runtime non caricherà un assembly compilato con una versione di .NET Framework con numero di versione superiore a quello del runtime attualmente caricato.</span><span class="sxs-lookup"><span data-stu-id="25256-109">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="25256-110">Questo vale per la combinazione dei componenti numero principale e numero secondario del numero di versione.</span><span class="sxs-lookup"><span data-stu-id="25256-110">This applies to the combination of the major and minor components of the version number.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25256-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="25256-111">In This Section</span></span>  
 [<span data-ttu-id="25256-112">Creazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="25256-112">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 <span data-ttu-id="25256-113">Offre una panoramica degli assembly a file singolo e su più file.</span><span class="sxs-lookup"><span data-stu-id="25256-113">Provides an overview of single-file and multifile assemblies.</span></span>  
  
 [<span data-ttu-id="25256-114">Nomi degli assembly</span><span class="sxs-lookup"><span data-stu-id="25256-114">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)  
 <span data-ttu-id="25256-115">Offre una panoramica dell'assegnazione dei nomi agli assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-115">Provides an overview of assembly naming.</span></span>  
  
 [<span data-ttu-id="25256-116">Procedura: Determinare il nome completo di un assembly</span><span class="sxs-lookup"><span data-stu-id="25256-116">How to: Determine an Assembly's Fully Qualified Name</span></span>](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 <span data-ttu-id="25256-117">Descrive come determinare il nome completo di un assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-117">Describes how to determine the fully qualified name of an assembly.</span></span>  
  
 [<span data-ttu-id="25256-118">Esecuzione di applicazioni Intranet in attendibilità totale</span><span class="sxs-lookup"><span data-stu-id="25256-118">Running Intranet Applications in Full Trust</span></span>](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 <span data-ttu-id="25256-119">Descrive come specificare criteri di sicurezza legacy per assembly con attendibilità totale in una condivisione di rete Intranet.</span><span class="sxs-lookup"><span data-stu-id="25256-119">Describes how to specify legacy security policy for full-trust assemblies on an intranet share.</span></span>  
  
 [<span data-ttu-id="25256-120">Posizione dell'assembly</span><span class="sxs-lookup"><span data-stu-id="25256-120">Assembly Location</span></span>](../../../docs/framework/app-domains/assembly-location.md)  
 <span data-ttu-id="25256-121">Offre una panoramica della posizione in cui si trovano gli assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-121">Provides an overview of where to locate assemblies.</span></span>  
  
 [<span data-ttu-id="25256-122">Procedura: Compilare un assembly su singolo file</span><span class="sxs-lookup"><span data-stu-id="25256-122">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 <span data-ttu-id="25256-123">Descrive come creare un assembly su singolo file.</span><span class="sxs-lookup"><span data-stu-id="25256-123">Describes how to create a single-file assembly.</span></span>  
  
 [<span data-ttu-id="25256-124">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="25256-124">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 <span data-ttu-id="25256-125">Descrive i motivi per la creazione di assembly su più file.</span><span class="sxs-lookup"><span data-stu-id="25256-125">Describes reasons for creating multifile assemblies.</span></span>  
  
 [<span data-ttu-id="25256-126">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="25256-126">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 <span data-ttu-id="25256-127">Descrive come creare un assembly su più file.</span><span class="sxs-lookup"><span data-stu-id="25256-127">Describes how to create a multifile assembly.</span></span>  
  
 [<span data-ttu-id="25256-128">Impostazione degli attributi dell'assembly</span><span class="sxs-lookup"><span data-stu-id="25256-128">Setting Assembly Attributes</span></span>](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 <span data-ttu-id="25256-129">Descrive gli attributi dell'assembly e come impostarli.</span><span class="sxs-lookup"><span data-stu-id="25256-129">Describes assembly attributes and how to set them.</span></span>  
  
 [<span data-ttu-id="25256-130">Creazione e utilizzo degli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="25256-130">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 <span data-ttu-id="25256-131">Descrive come e perché aggiungere un nome sicuro a un assembly e include procedure.</span><span class="sxs-lookup"><span data-stu-id="25256-131">Describes how and why you sign an assembly with a strong name, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="25256-132">Ritardo della firma di un assembly</span><span class="sxs-lookup"><span data-stu-id="25256-132">Delay Signing an Assembly</span></span>](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 <span data-ttu-id="25256-133">Descrive come ritardare la firma di un assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-133">Describes how to delay-sign an assembly.</span></span>  
  
 [<span data-ttu-id="25256-134">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="25256-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 <span data-ttu-id="25256-135">Descrive come e perché aggiungere assembly alla Global Assembly Cache e include argomenti relativi a procedure.</span><span class="sxs-lookup"><span data-stu-id="25256-135">Describes how and why you add assemblies to the global assembly cache, and includes how-to topics.</span></span>  
  
 [<span data-ttu-id="25256-136">Procedura: Visualizzare il contenuto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="25256-136">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 <span data-ttu-id="25256-137">Descrive come usare MSIL Disassembler (Ildasm.exe) per visualizzare il contenuto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-137">Describes how to use the MSIL Disassembler (Ildasm.exe) to view assembly contents.</span></span>  
  
 [<span data-ttu-id="25256-138">Inoltro dei tipi in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="25256-138">Type Forwarding in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 <span data-ttu-id="25256-139">Descrive come usare l'inoltro del tipo per spostare un tipo in un assembly diverso senza compromettere il funzionamento delle applicazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="25256-139">Describes how to use type forwarding to move a type into a different assembly without breaking existing applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="25256-140">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="25256-140">Reference</span></span>  
 <xref:System.Reflection.Assembly>  
 <span data-ttu-id="25256-141">Classe di .NET Framework che rappresenta un assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-141">The .NET Framework class that represents an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="25256-142">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="25256-142">Related Sections</span></span>  
 [<span data-ttu-id="25256-143">Procedura: Reperire informazioni su tipo e membro da un assembly</span><span class="sxs-lookup"><span data-stu-id="25256-143">How to: Obtain Type and Member Information from an Assembly</span></span>](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 <span data-ttu-id="25256-144">Descrive come ottenere a livello di codice il tipo e altre informazioni relative a un assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-144">Describes how to programmatically obtain type and other information from an assembly.</span></span>  
  
 [<span data-ttu-id="25256-145">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="25256-145">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="25256-146">Offre una panoramica concettuale sugli assembly Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="25256-146">Provides a conceptual overview of common language runtime assemblies.</span></span>  
  
 [<span data-ttu-id="25256-147">Controllo delle versioni degli assembly</span><span class="sxs-lookup"><span data-stu-id="25256-147">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)  
 <span data-ttu-id="25256-148">Offre una panoramica dell'associazione di assembly e degli attributi <xref:System.Reflection.AssemblyVersionAttribute> e <xref:System.Reflection.AssemblyInformationalVersionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="25256-148">Provides an overview of assembly binding and of the <xref:System.Reflection.AssemblyVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes.</span></span>  
  
 [<span data-ttu-id="25256-149">Come il runtime individua gli assembly</span><span class="sxs-lookup"><span data-stu-id="25256-149">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 <span data-ttu-id="25256-150">Descrive come il runtime determina l'assembly da usare per eseguire una richiesta di associazione.</span><span class="sxs-lookup"><span data-stu-id="25256-150">Describes how the runtime determines which assembly to use to fulfill a binding request.</span></span>  
  
 [<span data-ttu-id="25256-151">Reflection</span><span class="sxs-lookup"><span data-stu-id="25256-151">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="25256-152">Descrive come usare la classe **Reflection** per ottenere informazioni su un assembly.</span><span class="sxs-lookup"><span data-stu-id="25256-152">Describes how to use the **Reflection** class to obtain information about an assembly.</span></span>
