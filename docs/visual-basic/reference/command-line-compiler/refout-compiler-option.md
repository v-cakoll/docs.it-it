---
title: -refout
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 3649a24a52cc6a448ea7cf4d850915adf02147fb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348659"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="6a654-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a654-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="6a654-103">L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output.</span><span class="sxs-lookup"><span data-stu-id="6a654-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="6a654-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a654-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="6a654-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6a654-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="6a654-106">Percorso e nome del file dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="6a654-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="6a654-107">In genere dovrebbe trovarsi in una sottocartella dell'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="6a654-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="6a654-108">La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="6a654-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="6a654-109">Tutte le cartelle `filepath` in devono esistere; il compilatore non li crea.</span><span class="sxs-lookup"><span data-stu-id="6a654-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="6a654-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6a654-110">Remarks</span></span>

<span data-ttu-id="6a654-111">Visual Basic supporta l' `-refout` opzione che inizia con la versione 15,3.</span><span class="sxs-lookup"><span data-stu-id="6a654-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="6a654-112">Gli assembly di riferimento sono un tipo speciale di assembly che contiene solo la quantità minima di metadati necessaria per rappresentare la superficie dell'API pubblica della libreria.</span><span class="sxs-lookup"><span data-stu-id="6a654-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="6a654-113">Sono incluse le dichiarazioni per tutti i membri significativi quando si fa riferimento a un assembly negli strumenti di compilazione, ma si escludono tutte le implementazioni e le dichiarazioni dei membri privati che non hanno alcun impatto osservabile sul contratto API.</span><span class="sxs-lookup"><span data-stu-id="6a654-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="6a654-114">Per ulteriori informazioni, vedere [assembly di riferimento](../../../standard/assembly/reference-assemblies.md) nella Guida di .NET.</span><span class="sxs-lookup"><span data-stu-id="6a654-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="6a654-115">Le `-refout` opzioni [`-refonly`](refonly-compiler-option.md) e si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="6a654-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a654-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="6a654-116">See also</span></span>

- [<span data-ttu-id="6a654-117">-refonly</span><span class="sxs-lookup"><span data-stu-id="6a654-117">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="6a654-118">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a654-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6a654-119">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="6a654-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
