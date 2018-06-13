---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8f6c15084ac9b1a07aef8a0311edfcc4a93337c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653046"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="1cc7c-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1cc7c-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="1cc7c-103">Il **- refonly** opzione indica che l'output primario della compilazione deve essere un assembly di riferimento anziché un'implementazione.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="1cc7c-104">Il parametro `-refonly` disabilita automaticamente l'output dei file PDB poiché non è possibile eseguire gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="1cc7c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1cc7c-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="1cc7c-106">Note</span><span class="sxs-lookup"><span data-stu-id="1cc7c-106">Remarks</span></span>

<span data-ttu-id="1cc7c-107">Visual Basic supporta i `-refout` passare a partire dalla versione 15.3.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-107">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="1cc7c-108">Gli assembly di riferimento sono solo di metadati che contengono metadati ma nessun codice di implementazione.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-108">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="1cc7c-109">È incluso il tipo e membro informazioni per tutte le funzioni ad eccezione dei tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-109">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="1cc7c-110">L'utilizzo di corpi `throw null`, a differenza di nessun corpo, è giustificato dal fatto che PEVerify può essere eseguito e avere esito positivo convalidando la completezza dei metadati.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-110">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="1cc7c-111">Gli assembly di riferimento includono un livello di assembly [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attributo.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-111">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="1cc7c-112">Questo attributo può essere specificato nell'origine, quindi non è necessaria la sintesi da parte del compilatore.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-112">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="1cc7c-113">A causa di questo attributo, il runtime non caricherà gli assembly di riferimento per l'esecuzione (ma possono comunque essere caricati in un contesto reflection-only).</span><span class="sxs-lookup"><span data-stu-id="1cc7c-113">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="1cc7c-114">Strumenti che riflettono sugli assembly necessario verificare che vengano caricati gli assembly di riferimento come ReflectionOnly; in caso contrario, il runtime genera un <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-114">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="1cc7c-115">Le opzioni `-refonly` e [`-refout`](refout-compiler-option.md) si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="1cc7c-115">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cc7c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cc7c-116">See also</span></span>
<span data-ttu-id="1cc7c-117">[-refout](refout-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="1cc7c-117">[-refout](refout-compiler-option.md) </span></span>  
[<span data-ttu-id="1cc7c-118">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1cc7c-118">Visual Basic Command-Line Compiler</span></span>](index.md)  
[<span data-ttu-id="1cc7c-119">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="1cc7c-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)   
