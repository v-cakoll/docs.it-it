---
title: Identificatori di riga, di file e di percorso di origine
description: Informazioni su come usare predefinito F# valori di identificatore che consentono di accedere all'origine della riga numero, directory e nome file del codice.
ms.date: 05/16/2016
ms.openlocfilehash: 4b145fe1fe20e3d7f868558e33bab26204fb0125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663622"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="27fe8-103">Identificatori di riga, di file e di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="27fe8-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="27fe8-104">Gli identificatori `__LINE__`, `__SOURCE_DIRECTORY__` e `__SOURCE_FILE__` sono valori predefiniti che consentono di accedere al sorgente riga numero, directory e file di nome nel codice.</span><span class="sxs-lookup"><span data-stu-id="27fe8-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="27fe8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27fe8-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="27fe8-106">Note</span><span class="sxs-lookup"><span data-stu-id="27fe8-106">Remarks</span></span>

<span data-ttu-id="27fe8-107">Ognuno di questi valori ha tipo `string`.</span><span class="sxs-lookup"><span data-stu-id="27fe8-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="27fe8-108">La tabella seguente riepiloga gli identificatori di riga, file e percorso di origine disponibili in F#.</span><span class="sxs-lookup"><span data-stu-id="27fe8-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="27fe8-109">Questi identificatori non sono le macro del preprocessore; si tratta di valori predefiniti che sono riconosciuti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="27fe8-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="27fe8-110">Identificatore predefinito</span><span class="sxs-lookup"><span data-stu-id="27fe8-110">Predefined identifier</span></span>|<span data-ttu-id="27fe8-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="27fe8-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="27fe8-112">Restituisce il numero di riga corrente, prendere in considerazione `#line` direttive.</span><span class="sxs-lookup"><span data-stu-id="27fe8-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="27fe8-113">Restituisce il percorso corrente completo della directory di origine, prendere in considerazione `#line` direttive.</span><span class="sxs-lookup"><span data-stu-id="27fe8-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="27fe8-114">Restituisce il nome di file di origine corrente e il relativo percorso, prendere in considerazione `#line` direttive.</span><span class="sxs-lookup"><span data-stu-id="27fe8-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|

<span data-ttu-id="27fe8-115">Per altre informazioni sul `#line` direttiva, vedere [direttive del compilatore](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="27fe8-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="27fe8-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="27fe8-116">Example</span></span>

<span data-ttu-id="27fe8-117">Esempio di codice seguente viene illustrato l'utilizzo di questi valori.</span><span class="sxs-lookup"><span data-stu-id="27fe8-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="27fe8-118">Output:</span><span class="sxs-lookup"><span data-stu-id="27fe8-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="27fe8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27fe8-119">See also</span></span>

- [<span data-ttu-id="27fe8-120">Direttive per il compilatore</span><span class="sxs-lookup"><span data-stu-id="27fe8-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="27fe8-121">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="27fe8-121">F# Language Reference</span></span>](index.md)
