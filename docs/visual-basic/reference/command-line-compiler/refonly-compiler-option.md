---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775559"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="3fb6a-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3fb6a-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="3fb6a-103">L'opzione **-refonly** indica che l'output primario della compilazione deve essere un assembly di riferimento invece di un assembly di implementazione.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="3fb6a-104">Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="3fb6a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fb6a-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="3fb6a-106">Note</span><span class="sxs-lookup"><span data-stu-id="3fb6a-106">Remarks</span></span>

<span data-ttu-id="3fb6a-107">Visual Basic supporta l'opzione di `-refonly` a partire dalla versione 15,3.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="3fb6a-108">Gli assembly di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie dell'API pubblica della libreria.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="3fb6a-109">Sono incluse le dichiarazioni per tutti i membri significativi quando si fa riferimento a un assembly negli strumenti di compilazione, ma si escludono tutte le implementazioni e le dichiarazioni dei membri privati che non hanno alcun impatto osservabile sul contratto API.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="3fb6a-110">Per ulteriori informazioni, vedere [assembly di riferimento](../../../standard/assembly/reference-assemblies.md) nella Guida di .NET.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="3fb6a-111">Le opzioni `-refonly` e [`-refout`](refout-compiler-option.md) si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="3fb6a-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fb6a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fb6a-112">See also</span></span>

- [<span data-ttu-id="3fb6a-113">/refout</span><span class="sxs-lookup"><span data-stu-id="3fb6a-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="3fb6a-114">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3fb6a-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="3fb6a-115">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="3fb6a-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
