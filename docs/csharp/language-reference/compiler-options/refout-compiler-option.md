---
title: -refout (opzioni del compilatore C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72771764"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="374a0-102">-refout (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="374a0-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="374a0-103">L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output.</span><span class="sxs-lookup"><span data-stu-id="374a0-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="374a0-104">Ciò si converte in `metadataPeStream` nell'API Emit.</span><span class="sxs-lookup"><span data-stu-id="374a0-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="374a0-105">Questa opzione corrisponde alla proprietà del progetto [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="374a0-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="374a0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="374a0-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="374a0-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="374a0-107">Arguments</span></span>

 <span data-ttu-id="374a0-108">`filepath` Il percorso del file dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="374a0-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="374a0-109">In genere corrisponde a quello dell'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="374a0-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="374a0-110">La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="374a0-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="374a0-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="374a0-111">Remarks</span></span>

<span data-ttu-id="374a0-112">Gli assembly di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie API pubblica della libreria.</span><span class="sxs-lookup"><span data-stu-id="374a0-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="374a0-113">Includono dichiarazioni per tutti i membri che sono significative quando si fa riferimento a un assembly negli strumenti di compilazione, ma escludono tutte le implementazioni dei membri e le dichiarazioni di membri privati che non hanno alcun impatto osservabile sul contratto API.</span><span class="sxs-lookup"><span data-stu-id="374a0-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="374a0-114">Per altre informazioni, vedere Assembly di [riferimento](../../../standard/assembly/reference-assemblies.md) nella Guida di .NET.</span><span class="sxs-lookup"><span data-stu-id="374a0-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="374a0-115">Le `-refout` [`-refonly`](refonly-compiler-option.md) opzioni e si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="374a0-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="374a0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="374a0-116">See also</span></span>

- [<span data-ttu-id="374a0-117">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="374a0-117">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="374a0-118">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="374a0-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
