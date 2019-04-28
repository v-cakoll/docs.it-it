---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: f2cdd228d8ce1912abbbe888c29c42f29299ebba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788791"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="757ba-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="757ba-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="757ba-103">L'opzione **-refout** specifica un percorso file in cui l'assembly di riferimento deve essere restituito come output.</span><span class="sxs-lookup"><span data-stu-id="757ba-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="757ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="757ba-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="757ba-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="757ba-105">Arguments</span></span>

 <span data-ttu-id="757ba-106">`filepath` Il percorso e nome file dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="757ba-106">`filepath` The path and filename of the reference assembly.</span></span> <span data-ttu-id="757ba-107">In genere deve essere in una sottocartella dell'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="757ba-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="757ba-108">La convenzione consigliata (usata da MSBuild) consiste nell'inserire l'assembly di riferimento in una sottocartella "ref /" relativa all'assembly primario.</span><span class="sxs-lookup"><span data-stu-id="757ba-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="757ba-109">Tutte le cartelle in `filepath` deve esistere; il compilatore non vengono create.</span><span class="sxs-lookup"><span data-stu-id="757ba-109">All folders in `filepath` must exist; the compiler does not create them.</span></span> 

## <a name="remarks"></a><span data-ttu-id="757ba-110">Note</span><span class="sxs-lookup"><span data-stu-id="757ba-110">Remarks</span></span>

<span data-ttu-id="757ba-111">Visual Basic supporta il `-refout` passare a partire dalla versione 15.3.</span><span class="sxs-lookup"><span data-stu-id="757ba-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="757ba-112">Gli assembly di riferimento sono solo di metadati che contiene metadati ma nessun codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="757ba-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="757ba-113">Includono informazioni su tipo e membro per tutto, tranne i tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="757ba-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="757ba-114">I corpi di metodo vengono sostituiti con un singolo `throw null` istruzione.</span><span class="sxs-lookup"><span data-stu-id="757ba-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="757ba-115">Il motivo per usare `throw null` corpi di metodo (in contrapposizione nessun corpo) è in modo che PEVerify può eseguire e passare (convalidando la completezza dei metadati).</span><span class="sxs-lookup"><span data-stu-id="757ba-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="757ba-116">Gli assembly di riferimento includono un livello di assembly [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attributo.</span><span class="sxs-lookup"><span data-stu-id="757ba-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="757ba-117">Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore.</span><span class="sxs-lookup"><span data-stu-id="757ba-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="757ba-118">A causa di questo attributo, i runtime rifiutano di caricare gli assembly di riferimento per l'esecuzione (ma possono comunque essere caricati in un contesto reflection-only).</span><span class="sxs-lookup"><span data-stu-id="757ba-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="757ba-119">Gli strumenti che riflettono sugli assembly devono garantire che vengano caricati gli assembly di riferimento come sola reflection; in caso contrario, il runtime genera una <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="757ba-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="757ba-120">Le opzioni `-refout` e [`-refonly`](refonly-compiler-option.md) si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="757ba-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="757ba-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="757ba-121">See also</span></span>

- [<span data-ttu-id="757ba-122">/refonly</span><span class="sxs-lookup"><span data-stu-id="757ba-122">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="757ba-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="757ba-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="757ba-124">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="757ba-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
