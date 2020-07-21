---
title: Creazione di assembly e metodi dinamici
description: Creare assembly e metodi dinamici utilizzando lo spazio dei nomi System. Reflection. Emit, che consente a un compilatore o a uno strumento di creare metadati e codice MSIL in fase di esecuzione.
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: 76d2a83943d9df06cc66cf86c6869f18fac2a12c
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475047"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="c8056-103">Creazione di assembly e metodi dinamici</span><span class="sxs-lookup"><span data-stu-id="c8056-103">Emitting Dynamic Methods and Assemblies</span></span>

<span data-ttu-id="c8056-104">Questa sezione descrive un insieme di tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit> che consentono la creazione di metadati e codice MSIL (Microsoft Intermediate Language) da parte di compilatori o strumenti in fase di esecuzione ed eventualmente la generazione su disco di un file eseguibile portabile (PE, Portable Executable).</span><span class="sxs-lookup"><span data-stu-id="c8056-104">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="c8056-105">Questo spazio dei nomi viene usato principalmente da moduli di gestione di script e compilatori.</span><span class="sxs-lookup"><span data-stu-id="c8056-105">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="c8056-106">In questa sezione si farà riferimento alle funzionalità fornite dallo spazio dei nomi <xref:System.Reflection.Emit> con l'espressione reflection emit (creazione tramite la reflection). </span><span class="sxs-lookup"><span data-stu-id="c8056-106">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
<span data-ttu-id="c8056-107">La reflection emit offre le funzionalità seguenti: </span><span class="sxs-lookup"><span data-stu-id="c8056-107">Reflection emit provides the following capabilities:</span></span>  
  
- <span data-ttu-id="c8056-108">Definizione di metodi globali di tipo lightweight in fase di esecuzione mediante la classe <xref:System.Reflection.Emit.DynamicMethod> ed esecuzione di tali metodi mediante delegati.</span><span class="sxs-lookup"><span data-stu-id="c8056-108">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
- <span data-ttu-id="c8056-109">Definizione di assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.</span><span class="sxs-lookup"><span data-stu-id="c8056-109">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
- <span data-ttu-id="c8056-110">Definizione di assembly in fase di esecuzione, quindi esecuzione e scaricamento per consentire al processo di Garbage Collection di recuperare le risorse.</span><span class="sxs-lookup"><span data-stu-id="c8056-110">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
- <span data-ttu-id="c8056-111">Definizione di moduli in nuovi assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.</span><span class="sxs-lookup"><span data-stu-id="c8056-111">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
- <span data-ttu-id="c8056-112">Definizione di tipi in moduli in fase di esecuzione, creazione di istanze di tali tipi e chiamate ai relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="c8056-112">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
- <span data-ttu-id="c8056-113">Definizione di informazioni relative ai simboli per i moduli definiti, che possono essere usate da strumenti quali debugger e analizzatori di codice.</span><span class="sxs-lookup"><span data-stu-id="c8056-113">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
<span data-ttu-id="c8056-114">Oltre ai tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit>, sono disponibili interfacce di metadati non gestite, descritte nella documentazione di riferimento per le [interfacce di metadati](../unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="c8056-114">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="c8056-115">La reflection emit gestita garantisce un controllo degli errori semantici più completo e un livello di astrazione dei metadati più alto rispetto alle interfacce di metadati non gestite.</span><span class="sxs-lookup"><span data-stu-id="c8056-115">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
<span data-ttu-id="c8056-116">Un'altra risorsa per l'uso di metadati e codice MSIL è la documentazione CLI (Common Language Infrastructure), in particolare la seconda e la terza parte, relative rispettivamente alla semantica e alla definizione dei metadati e all'insieme di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c8056-116">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="c8056-117">La documentazione è disponibile online nel [sito Web ECMA](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="c8056-117">The documentation is available online at the [Ecma Web site](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8056-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c8056-118">In This Section</span></span>
  
[<span data-ttu-id="c8056-119">Problemi di sicurezza nella Reflection Emit</span><span class="sxs-lookup"><span data-stu-id="c8056-119">Security issues in reflection emit</span></span>](security-issues-in-reflection-emit.md)  
<span data-ttu-id="c8056-120">Descrive i problemi di sicurezza relativi alla creazione di assembly dinamici mediante la reflection emit.</span><span class="sxs-lookup"><span data-stu-id="c8056-120">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="c8056-121">[Procedura: definire ed eseguire metodi dinamici](how-to-define-and-execute-dynamic-methods.md) Viene illustrato come eseguire un metodo dinamico semplice e un metodo dinamico associato a un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="c8056-121">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="c8056-122">[Procedura: definire un tipo generico tramite reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) Viene illustrato come creare un tipo generico semplice con due parametri di tipo, come applicare vincoli di classe, interfaccia e speciali ai parametri di tipo e come creare membri che usano i parametri di tipo della classe come tipi di parametro e tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="c8056-122">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="c8056-123">[Procedura: definire un metodo generico tramite reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) Viene illustrato come creare, emettere e richiamare un metodo generico semplice.</span><span class="sxs-lookup"><span data-stu-id="c8056-123">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="c8056-124">Assembly ritirabili [per la generazione di tipi dinamici](collectible-assemblies.md) Introduce assembly ritirabili, che sono assembly dinamici che possono essere scaricati senza scaricare il dominio dell'applicazione in cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="c8056-124">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="c8056-125">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="c8056-125">Reference</span></span>  

<xref:System.Reflection.Emit.OpCodes>  
<span data-ttu-id="c8056-126">Cataloga i codici di istruzioni MSIL che è possibile usare per compilare i corpi dei metodi.</span><span class="sxs-lookup"><span data-stu-id="c8056-126">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
<xref:System.Reflection.Emit>  
<span data-ttu-id="c8056-127">Contiene le classi gestite usate per creare metodi, assembly e tipi dinamici.</span><span class="sxs-lookup"><span data-stu-id="c8056-127">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
<xref:System.Type>  
<span data-ttu-id="c8056-128">Illustra la classe <xref:System.Type>, che rappresenta i tipi nella reflection gestita e nella reflection emit, e descrive i concetti fondamentali relativi all'uso di queste tecnologie.</span><span class="sxs-lookup"><span data-stu-id="c8056-128">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
<xref:System.Reflection>  
<span data-ttu-id="c8056-129">Contiene le classi gestite usate per esaminare i metadati e il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c8056-129">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c8056-130">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c8056-130">Related Sections</span></span>  

[<span data-ttu-id="c8056-131">Reflection</span><span class="sxs-lookup"><span data-stu-id="c8056-131">Reflection</span></span>](reflection.md)  
<span data-ttu-id="c8056-132">Illustra come esaminare i metadati e il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c8056-132">Explains how to explore metadata and managed code.</span></span>  
  
[<span data-ttu-id="c8056-133">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="c8056-133">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="c8056-134">Fornisce una panoramica degli assembly nelle implementazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="c8056-134">Provides an overview of assemblies in .NET implementations.</span></span>
