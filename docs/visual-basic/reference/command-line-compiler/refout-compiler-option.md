---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582864"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="11f90-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11f90-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="11f90-103">L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output.</span><span class="sxs-lookup"><span data-stu-id="11f90-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="11f90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="11f90-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="11f90-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="11f90-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="11f90-106">Percorso e nome del file dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="11f90-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="11f90-107">In genere dovrebbe trovarsi in una sottocartella dell'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="11f90-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="11f90-108">La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="11f90-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="11f90-109">Tutte le cartelle nel `filepath` devono esistere; il compilatore non li crea.</span><span class="sxs-lookup"><span data-stu-id="11f90-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="11f90-110">Note</span><span class="sxs-lookup"><span data-stu-id="11f90-110">Remarks</span></span>

<span data-ttu-id="11f90-111">Visual Basic supporta l'opzione di `-refout` a partire dalla versione 15,3.</span><span class="sxs-lookup"><span data-stu-id="11f90-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="11f90-112">Gli assembly di riferimento sono assembly di soli metadati che contengono metadati ma nessun codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="11f90-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="11f90-113">Includono informazioni sul tipo e sui membri per tutti gli elementi eccetto i tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="11f90-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="11f90-114">I corpi dei metodi vengono sostituiti con una singola istruzione `throw null`.</span><span class="sxs-lookup"><span data-stu-id="11f90-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="11f90-115">Il motivo per cui si usano i corpi del metodo `throw null` (in contrapposizione a nessun corpo) è in modo che PEVerify possa essere eseguito e superato (convalidando quindi la completezza dei metadati).</span><span class="sxs-lookup"><span data-stu-id="11f90-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="11f90-116">Gli assembly di riferimento includono un attributo [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="11f90-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="11f90-117">Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore.</span><span class="sxs-lookup"><span data-stu-id="11f90-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="11f90-118">A causa di questo attributo, i runtime rifiutano di caricare gli assembly di riferimento per l'esecuzione, ma possono comunque essere caricati in un contesto di sola reflection.</span><span class="sxs-lookup"><span data-stu-id="11f90-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="11f90-119">Gli strumenti che riflettono gli assembly devono assicurarsi di caricare gli assembly di riferimento come solo reflection; in caso contrario, il runtime genera un'<xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="11f90-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="11f90-120">Le opzioni `-refout` e [`-refonly`](refonly-compiler-option.md) si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="11f90-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="11f90-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11f90-121">See also</span></span>

- [<span data-ttu-id="11f90-122">/refonly</span><span class="sxs-lookup"><span data-stu-id="11f90-122">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="11f90-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11f90-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="11f90-124">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="11f90-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
