---
title: Creazione di assembly e metodi dinamici
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: fda5a20eb7798086ec10415889454b4a8beba5f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180532"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="34eee-102">Creazione di assembly e metodi dinamici</span><span class="sxs-lookup"><span data-stu-id="34eee-102">Emitting Dynamic Methods and Assemblies</span></span>

<span data-ttu-id="34eee-103">Questa sezione descrive un insieme di tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit> che consentono la creazione di metadati e codice MSIL (Microsoft Intermediate Language) da parte di compilatori o strumenti in fase di esecuzione ed eventualmente la generazione su disco di un file eseguibile portabile (PE, Portable Executable).</span><span class="sxs-lookup"><span data-stu-id="34eee-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="34eee-104">Questo spazio dei nomi viene usato principalmente da moduli di gestione di script e compilatori.</span><span class="sxs-lookup"><span data-stu-id="34eee-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="34eee-105">In questa sezione si farà riferimento alle funzionalità fornite dallo spazio dei nomi <xref:System.Reflection.Emit> con l'espressione reflection emit (creazione tramite la reflection). </span><span class="sxs-lookup"><span data-stu-id="34eee-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
<span data-ttu-id="34eee-106">La reflection emit offre le funzionalità seguenti: </span><span class="sxs-lookup"><span data-stu-id="34eee-106">Reflection emit provides the following capabilities:</span></span>  
  
- <span data-ttu-id="34eee-107">Definizione di metodi globali di tipo lightweight in fase di esecuzione mediante la classe <xref:System.Reflection.Emit.DynamicMethod> ed esecuzione di tali metodi mediante delegati.</span><span class="sxs-lookup"><span data-stu-id="34eee-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
- <span data-ttu-id="34eee-108">Definizione di assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.</span><span class="sxs-lookup"><span data-stu-id="34eee-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
- <span data-ttu-id="34eee-109">Definizione di assembly in fase di esecuzione, quindi esecuzione e scaricamento per consentire al processo di Garbage Collection di recuperare le risorse.</span><span class="sxs-lookup"><span data-stu-id="34eee-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
- <span data-ttu-id="34eee-110">Definizione di moduli in nuovi assembly in fase di esecuzione, quindi esecuzione e/o salvataggio di tali assembly su disco.</span><span class="sxs-lookup"><span data-stu-id="34eee-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
- <span data-ttu-id="34eee-111">Definizione di tipi in moduli in fase di esecuzione, creazione di istanze di tali tipi e chiamate ai relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="34eee-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
- <span data-ttu-id="34eee-112">Definizione di informazioni relative ai simboli per i moduli definiti, che possono essere usate da strumenti quali debugger e analizzatori di codice.</span><span class="sxs-lookup"><span data-stu-id="34eee-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
<span data-ttu-id="34eee-113">Oltre ai tipi gestiti dello spazio dei nomi <xref:System.Reflection.Emit>, sono disponibili interfacce di metadati non gestite, descritte nella documentazione di riferimento per le [interfacce di metadati](../unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="34eee-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="34eee-114">La reflection emit gestita garantisce un controllo degli errori semantici più completo e un livello di astrazione dei metadati più alto rispetto alle interfacce di metadati non gestite.</span><span class="sxs-lookup"><span data-stu-id="34eee-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
<span data-ttu-id="34eee-115">Un'altra risorsa per l'uso di metadati e codice MSIL è la documentazione CLI (Common Language Infrastructure), in particolare la seconda e la terza parte, relative rispettivamente alla semantica e alla definizione dei metadati e all'insieme di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="34eee-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="34eee-116">La documentazione è disponibile online sul [sito Web Ecma](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="34eee-116">The documentation is available online at the [Ecma Web site](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="34eee-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="34eee-117">In This Section</span></span>
  
[<span data-ttu-id="34eee-118">Problemi di sicurezza in reflection emettono</span><span class="sxs-lookup"><span data-stu-id="34eee-118">Security issues in reflection emit</span></span>](security-issues-in-reflection-emit.md)  
<span data-ttu-id="34eee-119">Descrive i problemi di sicurezza relativi alla creazione di assembly dinamici mediante la reflection emit.</span><span class="sxs-lookup"><span data-stu-id="34eee-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="34eee-120">[Procedura: definire ed eseguire metodi dinamiciHow to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) Viene illustrato come eseguire un metodo dinamico semplice e un metodo dinamico associato a un'istanza di una classe.</span><span class="sxs-lookup"><span data-stu-id="34eee-120">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="34eee-121">[Procedura: definire un tipo generico con reflection emitHow to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) Viene illustrato come creare un tipo generico semplice con due parametri di tipo, come applicare vincoli di classe, interfaccia e speciali ai parametri di tipo e come creare membri che utilizzano i parametri di tipo della classe come tipi di parametro e tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="34eee-121">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create members that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="34eee-122">[Procedura: definire un metodo generico con emit di reflectionHow to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) Viene illustrato come creare, generare e richiamare un metodo generico semplice.</span><span class="sxs-lookup"><span data-stu-id="34eee-122">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="34eee-123">[Assembly ritirabili per la generazione dinamica di tipiCollectible assemblies for dynamic type generation](collectible-assemblies.md) Introduce assembly ritirabili, ovvero assembly dinamici che possono essere scaricati senza scaricare il dominio applicazione in cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="34eee-123">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="34eee-124">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="34eee-124">Reference</span></span>  

<xref:System.Reflection.Emit.OpCodes>  
<span data-ttu-id="34eee-125">Cataloga i codici di istruzioni MSIL che è possibile usare per compilare i corpi dei metodi.</span><span class="sxs-lookup"><span data-stu-id="34eee-125">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
<xref:System.Reflection.Emit>  
<span data-ttu-id="34eee-126">Contiene le classi gestite usate per creare metodi, assembly e tipi dinamici.</span><span class="sxs-lookup"><span data-stu-id="34eee-126">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
<xref:System.Type>  
<span data-ttu-id="34eee-127">Illustra la classe <xref:System.Type>, che rappresenta i tipi nella reflection gestita e nella reflection emit, e descrive i concetti fondamentali relativi all'uso di queste tecnologie.</span><span class="sxs-lookup"><span data-stu-id="34eee-127">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
<xref:System.Reflection>  
<span data-ttu-id="34eee-128">Contiene le classi gestite usate per esaminare i metadati e il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="34eee-128">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="34eee-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="34eee-129">Related Sections</span></span>  

[<span data-ttu-id="34eee-130">Riflessione</span><span class="sxs-lookup"><span data-stu-id="34eee-130">Reflection</span></span>](reflection.md)  
<span data-ttu-id="34eee-131">Illustra come esaminare i metadati e il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="34eee-131">Explains how to explore metadata and managed code.</span></span>  
  
[<span data-ttu-id="34eee-132">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="34eee-132">Assemblies in .NET</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="34eee-133">Fornisce una panoramica degli assembly nelle implementazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="34eee-133">Provides an overview of assemblies in .NET implementations.</span></span>
