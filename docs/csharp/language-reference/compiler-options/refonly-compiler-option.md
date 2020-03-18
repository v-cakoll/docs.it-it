---
title: -refonly (opzioni del compilatore C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: 856b65d3b2217dbe5d53ecda00723b47247d80a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72773857"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="9097f-102">-refonly (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="9097f-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="9097f-103">L'opzione **-refonly** indica che l'output primario deve essere un assembly di riferimento, anziché un assembly di implementazione.</span><span class="sxs-lookup"><span data-stu-id="9097f-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="9097f-104">Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="9097f-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="9097f-105">Questa opzione corrisponde alla proprietà del progetto [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="9097f-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="9097f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9097f-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="9097f-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9097f-107">Remarks</span></span>

<span data-ttu-id="9097f-108">Gli assembly di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie API pubblica della libreria.</span><span class="sxs-lookup"><span data-stu-id="9097f-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="9097f-109">Includono dichiarazioni per tutti i membri che sono significative quando si fa riferimento a un assembly negli strumenti di compilazione, ma escludono tutte le implementazioni dei membri e le dichiarazioni di membri privati che non hanno alcun impatto osservabile sul contratto API.</span><span class="sxs-lookup"><span data-stu-id="9097f-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="9097f-110">Per altre informazioni, vedere Assembly di [riferimento](../../../standard/assembly/reference-assemblies.md) nella Guida di .NET.</span><span class="sxs-lookup"><span data-stu-id="9097f-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="9097f-111">Le `-refonly` [`-refout`](refout-compiler-option.md) opzioni e si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="9097f-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="9097f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9097f-112">See also</span></span>

- [<span data-ttu-id="9097f-113">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="9097f-113">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="9097f-114">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="9097f-114">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
