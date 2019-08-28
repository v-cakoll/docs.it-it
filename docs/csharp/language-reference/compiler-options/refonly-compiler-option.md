---
title: -refonly (opzioni del compilatore C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: eb62f98c5d548fe3583d3422eb7b6020a82c296a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606479"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="643b7-102">-refonly (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="643b7-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="643b7-103">L'opzione **-refonly** indica che l'output primario deve essere un assembly di riferimento, anziché un assembly di implementazione.</span><span class="sxs-lookup"><span data-stu-id="643b7-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="643b7-104">Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="643b7-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="643b7-105">Questa opzione corrisponde alla proprietà del progetto [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="643b7-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="643b7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="643b7-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="643b7-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="643b7-107">Remarks</span></span>

<span data-ttu-id="643b7-108">Per gli assembly di soli metadati i corpi di metodo vengono sostituiti con un singolo corpo `throw null`, ma sono inclusi tutti i membri, tranne i tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="643b7-108">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="643b7-109">L'utilizzo di corpi `throw null`, a differenza di nessun corpo, è giustificato dal fatto che PEVerify può essere eseguito e avere esito positivo convalidando la completezza dei metadati.</span><span class="sxs-lookup"><span data-stu-id="643b7-109">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="643b7-110">Gli assembly di riferimento includono un attributo `ReferenceAssembly` al livello assembly.</span><span class="sxs-lookup"><span data-stu-id="643b7-110">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="643b7-111">Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore.</span><span class="sxs-lookup"><span data-stu-id="643b7-111">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="643b7-112">A causa di questo attributo, i runtime non caricheranno gli assembly di riferimento per l'esecuzione, che tuttavia possono essere caricati in modalità sola reflection.</span><span class="sxs-lookup"><span data-stu-id="643b7-112">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="643b7-113">Gli strumenti che eseguono la reflection sugli assembly devono garantire che vengano caricati gli assembly di riferimento come sola reflection; in caso contrario il runtime visualizzerà un errore di caricamento del tipo.</span><span class="sxs-lookup"><span data-stu-id="643b7-113">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="643b7-114">Gli assembly di riferimento rimuovono ulteriormente i metadati (membri privati) dagli assembly di soli metadati:</span><span class="sxs-lookup"><span data-stu-id="643b7-114">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="643b7-115">Un assembly di riferimento include solo i riferimenti per i requisiti nella superficie dell'API.</span><span class="sxs-lookup"><span data-stu-id="643b7-115">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="643b7-116">L'assembly reale può includere riferimenti aggiuntivi relativi a implementazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="643b7-116">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="643b7-117">Ad esempio, l'assembly di riferimento per `class C { private void M() { dynamic d = 1; ... } }` non fa riferimento ai tipi necessari per `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="643b7-117">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="643b7-118">I membri-funzione privati (metodi, proprietà ed eventi) vengono rimossi quando la rimozione non impatta in maniera visibile sulla compilazione.</span><span class="sxs-lookup"><span data-stu-id="643b7-118">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="643b7-119">Se non esistono attributi <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, eseguire la stessa operazione per i membri-funzione interni.</span><span class="sxs-lookup"><span data-stu-id="643b7-119">If there are no <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="643b7-120">Negli assembly di riferimento vengono tuttavia mantenuti tutti i tipi, inclusi i tipi privati o nidificati.</span><span class="sxs-lookup"><span data-stu-id="643b7-120">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="643b7-121">Vengono mantenuti tutti gli attributi, persino quelli interni.</span><span class="sxs-lookup"><span data-stu-id="643b7-121">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="643b7-122">Vengono mantenuti tutti i metodi virtuali.</span><span class="sxs-lookup"><span data-stu-id="643b7-122">All virtual methods are kept.</span></span> <span data-ttu-id="643b7-123">Vengono mantenute le implementazioni esplicite di interfacce.</span><span class="sxs-lookup"><span data-stu-id="643b7-123">Explicit interface implementations are kept.</span></span> <span data-ttu-id="643b7-124">Vengono mantenuti gli eventi e le proprietà implementati in modo esplicito poiché le relative funzioni di accesso sono virtuali.</span><span class="sxs-lookup"><span data-stu-id="643b7-124">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="643b7-125">Vengono mantenuti tutti i campi di uno struct.</span><span class="sxs-lookup"><span data-stu-id="643b7-125">All fields of a struct are kept.</span></span> <span data-ttu-id="643b7-126">È un candidato per la rifinitura post-C#-7.1.</span><span class="sxs-lookup"><span data-stu-id="643b7-126">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="643b7-127">Le opzioni `-refonly` e [`-refout`](refout-compiler-option.md) si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="643b7-127">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="643b7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="643b7-128">See also</span></span>

- [<span data-ttu-id="643b7-129">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="643b7-129">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="643b7-130">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="643b7-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
