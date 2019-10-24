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
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773857"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="68a72-102">-refonly (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="68a72-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="68a72-103">L'opzione **-refonly** indica che l'output primario deve essere un assembly di riferimento, anziché un assembly di implementazione.</span><span class="sxs-lookup"><span data-stu-id="68a72-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="68a72-104">Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="68a72-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="68a72-105">Questa opzione corrisponde alla proprietà del progetto [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="68a72-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="68a72-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68a72-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="68a72-107">Note</span><span class="sxs-lookup"><span data-stu-id="68a72-107">Remarks</span></span>

<span data-ttu-id="68a72-108">Gli assembly di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie dell'API pubblica della libreria.</span><span class="sxs-lookup"><span data-stu-id="68a72-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="68a72-109">Sono incluse le dichiarazioni per tutti i membri significativi quando si fa riferimento a un assembly negli strumenti di compilazione, ma si escludono tutte le implementazioni e le dichiarazioni dei membri privati che non hanno alcun impatto osservabile sul contratto API.</span><span class="sxs-lookup"><span data-stu-id="68a72-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="68a72-110">Per ulteriori informazioni, vedere [assembly di riferimento](../../../standard/assembly/reference-assemblies.md) nella Guida di .NET.</span><span class="sxs-lookup"><span data-stu-id="68a72-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="68a72-111">Le opzioni `-refonly` e [`-refout`](refout-compiler-option.md) si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="68a72-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="68a72-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68a72-112">See also</span></span>

- [<span data-ttu-id="68a72-113">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="68a72-113">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="68a72-114">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="68a72-114">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
