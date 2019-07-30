---
title: Identificatori di riga, di file e di percorso di origine
description: Informazioni su come usare i valori di F# identificatore predefiniti che consentono di accedere al numero di riga, alla directory e al nome file del codice sorgente.
ms.date: 05/16/2016
ms.openlocfilehash: 5ff36210edc75370f8baf9ee7be057f3ac0c3979
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627122"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="c9e60-103">Identificatori di riga, di file e di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="c9e60-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="c9e60-104">Gli identificatori `__LINE__` `__SOURCE_DIRECTORY__` e`__SOURCE_FILE__` sono valori predefiniti che consentono di accedere al numero di riga, alla directory e al nome file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="c9e60-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="c9e60-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9e60-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="c9e60-106">Note</span><span class="sxs-lookup"><span data-stu-id="c9e60-106">Remarks</span></span>

<span data-ttu-id="c9e60-107">Ognuno di questi valori è di `string`tipo.</span><span class="sxs-lookup"><span data-stu-id="c9e60-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="c9e60-108">Nella tabella seguente sono riepilogati gli identificatori di riga, file e percorso di origine disponibili in F#.</span><span class="sxs-lookup"><span data-stu-id="c9e60-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="c9e60-109">Questi identificatori non sono macro del preprocessore; si tratta di valori predefiniti riconosciuti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="c9e60-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="c9e60-110">Identificatore predefinito</span><span class="sxs-lookup"><span data-stu-id="c9e60-110">Predefined identifier</span></span>|<span data-ttu-id="c9e60-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9e60-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="c9e60-112">Restituisce il numero di riga corrente, considerando `#line` le direttive.</span><span class="sxs-lookup"><span data-stu-id="c9e60-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="c9e60-113">Restituisce il percorso completo corrente della directory di origine, considerando `#line` le direttive.</span><span class="sxs-lookup"><span data-stu-id="c9e60-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="c9e60-114">Restituisce il nome del file di origine corrente, senza il relativo percorso, `#line` considerando le direttive.</span><span class="sxs-lookup"><span data-stu-id="c9e60-114">Evaluates to the current source file name, without its path, considering `#line` directives.</span></span>|

<span data-ttu-id="c9e60-115">Per ulteriori informazioni sulla `#line` direttiva, vedere direttive [del compilatore](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="c9e60-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="c9e60-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9e60-116">Example</span></span>

<span data-ttu-id="c9e60-117">Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo di questi valori.</span><span class="sxs-lookup"><span data-stu-id="c9e60-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="c9e60-118">Output:</span><span class="sxs-lookup"><span data-stu-id="c9e60-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a><span data-ttu-id="c9e60-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9e60-119">See also</span></span>

- [<span data-ttu-id="c9e60-120">Direttive per il compilatore</span><span class="sxs-lookup"><span data-stu-id="c9e60-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="c9e60-121">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="c9e60-121">F# Language Reference</span></span>](index.md)
