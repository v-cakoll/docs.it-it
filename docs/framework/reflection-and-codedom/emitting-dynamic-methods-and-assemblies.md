---
title: Creazione di assembly e metodi dinamici
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.assetid: 8e8e2631-62fd-40e7-a8ee-0039b06749bc
caps.latest.revision: 18
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c28a5b71a93ea5159adc73316771d490dbe0db87
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="af77d-102">Creazione di assembly e metodi dinamici</span><span class="sxs-lookup"><span data-stu-id="af77d-102">Emitting Dynamic Methods and Assemblies</span></span>
<span data-ttu-id="af77d-103">Questa sezione descrive un insieme di tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit> che consentono la creazione di metadati e codice MSIL (Microsoft Intermediate Language) da parte di compilatori o strumenti in fase di esecuzione ed eventualmente la generazione su disco di un file eseguibile portabile (PE, Portable Executable).</span><span class="sxs-lookup"><span data-stu-id="af77d-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="af77d-104">Questo spazio dei nomi viene usato principalmente da moduli di gestione di script e compilatori.</span><span class="sxs-lookup"><span data-stu-id="af77d-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="af77d-105">In questa sezione si farà riferimento alle funzionalità fornite dallo spazio dei nomi <xref:System.Reflection.Emit> con l'espressione reflection emit (creazione tramite la reflection). </span><span class="sxs-lookup"><span data-stu-id="af77d-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
 <span data-ttu-id="af77d-106">La reflection emit offre le funzionalità seguenti: </span><span class="sxs-lookup"><span data-stu-id="af77d-106">Reflection emit provides the following capabilities:</span></span>  
  
-   <span data-ttu-id="af77d-107">Definizione di metodi globali di tipo lightweight in fase di esecuzione mediante la classe <xref:System.Reflection.Emit.DynamicMethod> ed esecuzione di tali metodi mediante delegati.</span><span class="sxs-lookup"><span data-stu-id="af77d-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
-   <span data-ttu-id="af77d-108">Definizione di assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.</span><span class="sxs-lookup"><span data-stu-id="af77d-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="af77d-109">Definizione di assembly in fase di esecuzione, quindi esecuzione e scaricamento per consentire al processo di Garbage Collection di recuperare le risorse.</span><span class="sxs-lookup"><span data-stu-id="af77d-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
-   <span data-ttu-id="af77d-110">Definizione di moduli in nuovi assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.</span><span class="sxs-lookup"><span data-stu-id="af77d-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="af77d-111">Definizione di tipi in moduli in fase di esecuzione, creazione di istanze di tali tipi e chiamate ai relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="af77d-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
-   <span data-ttu-id="af77d-112">Definizione di informazioni relative ai simboli per i moduli definiti, che possono essere usate da strumenti quali debugger e analizzatori di codice.</span><span class="sxs-lookup"><span data-stu-id="af77d-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
 <span data-ttu-id="af77d-113">Oltre ai tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit>, sono disponibili interfacce di metadati non gestite, descritte nella documentazione di riferimento per le [interfacce di metadati](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="af77d-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="af77d-114">La reflection emit gestita garantisce un controllo degli errori semantici più completo e un livello di astrazione dei metadati più alto rispetto alle interfacce di metadati non gestite.</span><span class="sxs-lookup"><span data-stu-id="af77d-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
 <span data-ttu-id="af77d-115">Un'altra risorsa per l'uso di metadati e codice MSIL è la documentazione CLI (Common Language Infrastructure), in particolare la seconda e la terza parte, relative rispettivamente alla semantica e alla definizione dei metadati e all'insieme di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="af77d-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="af77d-116">La documentazione è disponibile online su [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) e sul [sito Web di ECMA](http://go.microsoft.com/fwlink/?LinkId=116487).</span><span class="sxs-lookup"><span data-stu-id="af77d-116">The documentation is available online on [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) and at the [Ecma Web site](http://go.microsoft.com/fwlink/?LinkId=116487).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af77d-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="af77d-117">In This Section</span></span>  
 [<span data-ttu-id="af77d-118">Problemi di sicurezza nella reflection emit</span><span class="sxs-lookup"><span data-stu-id="af77d-118">Security Issues in Reflection Emit</span></span>](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
 <span data-ttu-id="af77d-119">Descrive i problemi di sicurezza relativi alla creazione di assembly dinamici mediante la reflection emit.</span><span class="sxs-lookup"><span data-stu-id="af77d-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="af77d-120">Riferimento</span><span class="sxs-lookup"><span data-stu-id="af77d-120">Reference</span></span>  
 <xref:System.Reflection.Emit.OpCodes>  
 <span data-ttu-id="af77d-121">Cataloga i codici di istruzioni MSIL che è possibile usare per compilare i corpi dei metodi.</span><span class="sxs-lookup"><span data-stu-id="af77d-121">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
 <xref:System.Reflection.Emit>  
 <span data-ttu-id="af77d-122">Contiene le classi gestite usate per creare metodi, assembly e tipi dinamici.</span><span class="sxs-lookup"><span data-stu-id="af77d-122">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
 <xref:System.Type>  
 <span data-ttu-id="af77d-123">Illustra la classe <xref:System.Type>, che rappresenta i tipi nella reflection gestita e nella reflection emit, e descrive i concetti fondamentali relativi all'uso di queste tecnologie.</span><span class="sxs-lookup"><span data-stu-id="af77d-123">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
 <xref:System.Reflection>  
 <span data-ttu-id="af77d-124">Contiene le classi gestite usate per esaminare i metadati e il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="af77d-124">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="af77d-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="af77d-125">Related Sections</span></span>  
 [<span data-ttu-id="af77d-126">Reflection</span><span class="sxs-lookup"><span data-stu-id="af77d-126">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="af77d-127">Illustra come esaminare i metadati e il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="af77d-127">Explains how to explore metadata and managed code.</span></span>  
  
 [<span data-ttu-id="af77d-128">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="af77d-128">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="af77d-129">Fornisce una panoramica degli assembly in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af77d-129">Provides an overview of assemblies in the .NET Framework.</span></span>

