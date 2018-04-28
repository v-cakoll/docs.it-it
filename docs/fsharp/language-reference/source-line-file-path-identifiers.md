---
title: Identificatori di riga, file e percorso di origine (F#)
description: "Informazioni sull'utilizzo di F # identificatore valori incorporati che consentono di accedere il numero di riga di origine, directory e nome file del codice."
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 18a26f0aa0a0c1f9c0b448ec46eaebd540391324
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="bf988-103">Identificatori di riga, di file e di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="bf988-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="bf988-104">Gli identificatori `__LINE__`, `__SOURCE_DIRECTORY__` e `__SOURCE_FILE__` sono valori incorporati che consentono di accedere al origine riga numero, directory e file di nome nel codice.</span><span class="sxs-lookup"><span data-stu-id="bf988-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>


## <a name="syntax"></a><span data-ttu-id="bf988-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf988-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="bf988-106">Note</span><span class="sxs-lookup"><span data-stu-id="bf988-106">Remarks</span></span>
<span data-ttu-id="bf988-107">Ognuno di questi valori è di tipo `string`.</span><span class="sxs-lookup"><span data-stu-id="bf988-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="bf988-108">Nella tabella seguente vengono riepilogati la riga di codice sorgente, file e identificatori del percorso che sono disponibili in F #.</span><span class="sxs-lookup"><span data-stu-id="bf988-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="bf988-109">Questi identificatori non sono macro del preprocessore. sono valori predefiniti che sono riconosciuti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="bf988-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="bf988-110">Identificatore predefinito</span><span class="sxs-lookup"><span data-stu-id="bf988-110">Predefined identifier</span></span>|<span data-ttu-id="bf988-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf988-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="bf988-112">Restituisce il numero di riga corrente, prendere in considerazione `#line` direttive.</span><span class="sxs-lookup"><span data-stu-id="bf988-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="bf988-113">Restituisce il percorso corrente completo della directory di origine, prendere in considerazione `#line` direttive.</span><span class="sxs-lookup"><span data-stu-id="bf988-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="bf988-114">Restituisce il nome di file di origine corrente e il relativo percorso, prendere in considerazione `#line` direttive.</span><span class="sxs-lookup"><span data-stu-id="bf988-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="bf988-115">Per ulteriori informazioni sul `#line` direttiva, vedere [direttive del compilatore](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="bf988-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="bf988-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf988-116">Example</span></span>

<span data-ttu-id="bf988-117">Esempio di codice seguente viene illustrato l'utilizzo di questi valori.</span><span class="sxs-lookup"><span data-stu-id="bf988-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="bf988-118">Output:</span><span class="sxs-lookup"><span data-stu-id="bf988-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="bf988-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf988-119">See Also</span></span>
[<span data-ttu-id="bf988-120">Direttive per il compilatore</span><span class="sxs-lookup"><span data-stu-id="bf988-120">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="bf988-121">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="bf988-121">F# Language Reference</span></span>](index.md)
