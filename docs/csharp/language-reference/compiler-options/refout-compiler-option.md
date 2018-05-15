---
title: -refout (opzioni del compilatore C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: cb0e26b03841c093f223b3013a0d3c52ffd914c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="78413-102">-refout (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="78413-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="78413-103">L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output.</span><span class="sxs-lookup"><span data-stu-id="78413-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="78413-104">Ciò si converte in `metadataPeStream` nell'API Emit.</span><span class="sxs-lookup"><span data-stu-id="78413-104">This translates to `metadataPeStream` in the Emit API.</span></span>

## <a name="syntax"></a><span data-ttu-id="78413-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78413-105">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="78413-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="78413-106">Arguments</span></span>

 <span data-ttu-id="78413-107">`filepath` Il percorso del file dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="78413-107">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="78413-108">In genere corrisponde a quello dell'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="78413-108">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="78413-109">La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="78413-109">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="78413-110">Note</span><span class="sxs-lookup"><span data-stu-id="78413-110">Remarks</span></span>

<span data-ttu-id="78413-111">Per gli assembly di soli metadati i corpi di metodo vengono sostituiti con un singolo corpo `throw null`, ma sono inclusi tutti i membri, tranne i tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="78413-111">Metadata-only assemblies have their method bodies replaced with a single `throw null` body, but include all members except anonymous types.</span></span> <span data-ttu-id="78413-112">L'utilizzo di corpi `throw null`, a differenza di nessun corpo, è giustificato dal fatto che PEVerify può essere eseguito e avere esito positivo convalidando la completezza dei metadati.</span><span class="sxs-lookup"><span data-stu-id="78413-112">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="78413-113">Gli assembly di riferimento includono un attributo `ReferenceAssembly` al livello assembly.</span><span class="sxs-lookup"><span data-stu-id="78413-113">Reference assemblies include an assembly-level `ReferenceAssembly` attribute.</span></span> <span data-ttu-id="78413-114">Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore.</span><span class="sxs-lookup"><span data-stu-id="78413-114">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="78413-115">A causa di questo attributo, i runtime non caricheranno gli assembly di riferimento per l'esecuzione, che tuttavia possono essere caricati in modalità sola reflection.</span><span class="sxs-lookup"><span data-stu-id="78413-115">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in reflection-only mode).</span></span> <span data-ttu-id="78413-116">Gli strumenti che eseguono la reflection sugli assembly devono garantire che vengano caricati gli assembly di riferimento come sola reflection; in caso contrario il runtime visualizzerà un errore di caricamento del tipo.</span><span class="sxs-lookup"><span data-stu-id="78413-116">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only, otherwise they will receive a typeload error from the runtime.</span></span>

<span data-ttu-id="78413-117">Gli assembly di riferimento rimuovono ulteriormente i metadati (membri privati) dagli assembly di soli metadati:</span><span class="sxs-lookup"><span data-stu-id="78413-117">Reference assemblies further remove metadata (private members) from metadata-only assemblies:</span></span>

- <span data-ttu-id="78413-118">Un assembly di riferimento include solo i riferimenti per i requisiti nella superficie dell'API.</span><span class="sxs-lookup"><span data-stu-id="78413-118">A reference assembly only has references for what it needs in the API surface.</span></span> <span data-ttu-id="78413-119">L'assembly reale può includere riferimenti aggiuntivi relativi a implementazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="78413-119">The real assembly may have additional references related to specific implementations.</span></span> <span data-ttu-id="78413-120">Ad esempio, l'assembly di riferimento per `class C { private void M() { dynamic d = 1; ... } }` non fa riferimento ai tipi necessari per `dynamic`.</span><span class="sxs-lookup"><span data-stu-id="78413-120">For instance, the reference assembly for `class C { private void M() { dynamic d = 1; ... } }` does not reference any types required for `dynamic`.</span></span>
- <span data-ttu-id="78413-121">I membri-funzione privati (metodi, proprietà ed eventi) vengono rimossi quando la rimozione non impatta in maniera visibile sulla compilazione.</span><span class="sxs-lookup"><span data-stu-id="78413-121">Private function-members (methods, properties, and events) are removed in cases where their removal doesn't observably impact compilation.</span></span> <span data-ttu-id="78413-122">Se non esistono attributi `InternalsVisibleTo`, eseguire la stessa operazione per i membri-funzione interni.</span><span class="sxs-lookup"><span data-stu-id="78413-122">If there are no `InternalsVisibleTo` attributes, do the same for internal function-members.</span></span>
- <span data-ttu-id="78413-123">Negli assembly di riferimento vengono tuttavia mantenuti tutti i tipi, inclusi i tipi privati o nidificati.</span><span class="sxs-lookup"><span data-stu-id="78413-123">But all types (including private or nested types) are kept in reference assemblies.</span></span> <span data-ttu-id="78413-124">Vengono mantenuti tutti gli attributi, persino quelli interni.</span><span class="sxs-lookup"><span data-stu-id="78413-124">All attributes are kept (even internal ones).</span></span>
- <span data-ttu-id="78413-125">Vengono mantenuti tutti i metodi virtuali.</span><span class="sxs-lookup"><span data-stu-id="78413-125">All virtual methods are kept.</span></span> <span data-ttu-id="78413-126">Vengono mantenute le implementazioni esplicite di interfacce.</span><span class="sxs-lookup"><span data-stu-id="78413-126">Explicit interface implementations are kept.</span></span> <span data-ttu-id="78413-127">Vengono mantenuti gli eventi e le proprietà implementati in modo esplicito poiché le relative funzioni di accesso sono virtuali.</span><span class="sxs-lookup"><span data-stu-id="78413-127">Explicitly implemented properties and events are kept, as their accessors are virtual (and are therefore kept).</span></span>
- <span data-ttu-id="78413-128">Vengono mantenuti tutti i campi di uno struct.</span><span class="sxs-lookup"><span data-stu-id="78413-128">All fields of a struct are kept.</span></span> <span data-ttu-id="78413-129">È un candidato per la rifinitura post-C#-7.1.</span><span class="sxs-lookup"><span data-stu-id="78413-129">(This is a candidate for post-C#-7.1 refinement)</span></span>

<span data-ttu-id="78413-130">Le opzioni `-refout` e [`-refonly`](refonly-compiler-option.md) si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="78413-130">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="78413-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78413-131">See Also</span></span>
 [<span data-ttu-id="78413-132">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="78413-132">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="78413-133">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="78413-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
