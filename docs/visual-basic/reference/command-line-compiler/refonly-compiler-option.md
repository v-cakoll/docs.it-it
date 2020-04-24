---
title: -refonly
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b906178abf8d159083d95e41448596d512e857de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348570"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="13cd0-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13cd0-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="13cd0-103">L'opzione **-refonly** indica che l'output primario della compilazione deve essere un assembly di riferimento invece di un assembly di implementazione.</span><span class="sxs-lookup"><span data-stu-id="13cd0-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="13cd0-104">Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="13cd0-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="13cd0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13cd0-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="13cd0-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="13cd0-106">Remarks</span></span>

<span data-ttu-id="13cd0-107">Visual Basic supporta l' `-refonly` opzione che inizia con la versione 15,3.</span><span class="sxs-lookup"><span data-stu-id="13cd0-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="13cd0-108">Gli assembly di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie dell'API pubblica della libreria.</span><span class="sxs-lookup"><span data-stu-id="13cd0-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="13cd0-109">Sono incluse le dichiarazioni per tutti i membri significativi quando si fa riferimento a un assembly negli strumenti di compilazione, ma si escludono tutte le implementazioni e le dichiarazioni dei membri privati che non hanno alcun impatto osservabile sul contratto API.</span><span class="sxs-lookup"><span data-stu-id="13cd0-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="13cd0-110">Per ulteriori informazioni, vedere [assembly di riferimento](../../../standard/assembly/reference-assemblies.md) nella Guida di .NET.</span><span class="sxs-lookup"><span data-stu-id="13cd0-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="13cd0-111">Le `-refonly` opzioni [`-refout`](refout-compiler-option.md) e si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="13cd0-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="13cd0-112">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="13cd0-112">See also</span></span>

- [<span data-ttu-id="13cd0-113">-refout</span><span class="sxs-lookup"><span data-stu-id="13cd0-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="13cd0-114">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13cd0-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="13cd0-115">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="13cd0-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
