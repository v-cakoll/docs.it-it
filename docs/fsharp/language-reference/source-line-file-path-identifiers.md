---
title: Identificatori di riga, file e percorso di origine (F#)
description: 'Informazioni su come utilizzare F # identificatore valori predefiniti che consentono di accedere il numero di riga di origine, directory e nome file del codice.'
ms.date: 05/16/2016
ms.openlocfilehash: 14f710d1412c3420ec627dc30216ba2e89f16bcd
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865127"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="494dc-103">Identificatori di riga, di file e di percorso di origine</span><span class="sxs-lookup"><span data-stu-id="494dc-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="494dc-104">Gli identificatori `__LINE__`, `__SOURCE_DIRECTORY__` e `__SOURCE_FILE__` sono valori predefiniti che consentono di accedere al sorgente riga numero, directory e file di nome nel codice.</span><span class="sxs-lookup"><span data-stu-id="494dc-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="494dc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="494dc-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="494dc-106">Note</span><span class="sxs-lookup"><span data-stu-id="494dc-106">Remarks</span></span>

<span data-ttu-id="494dc-107">Ognuno di questi valori ha tipo `string`.</span><span class="sxs-lookup"><span data-stu-id="494dc-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="494dc-108">La tabella seguente riepiloga la riga di codice sorgente, file e gli identificatori di percorso che sono disponibili in F #.</span><span class="sxs-lookup"><span data-stu-id="494dc-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="494dc-109">Questi identificatori non sono le macro del preprocessore; si tratta di valori predefiniti che sono riconosciuti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="494dc-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="494dc-110">Identificatore predefinito</span><span class="sxs-lookup"><span data-stu-id="494dc-110">Predefined identifier</span></span>|<span data-ttu-id="494dc-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="494dc-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="494dc-112">Restituisce il numero di riga corrente, prendere in considerazione `#line` direttive.</span><span class="sxs-lookup"><span data-stu-id="494dc-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="494dc-113">Restituisce il percorso corrente completo della directory di origine, prendere in considerazione `#line` direttive.</span><span class="sxs-lookup"><span data-stu-id="494dc-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="494dc-114">Restituisce il nome di file di origine corrente e il relativo percorso, prendere in considerazione `#line` direttive.</span><span class="sxs-lookup"><span data-stu-id="494dc-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="494dc-115">Per altre informazioni sul `#line` direttiva, vedere [direttive del compilatore](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="494dc-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="494dc-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="494dc-116">Example</span></span>

<span data-ttu-id="494dc-117">Esempio di codice seguente viene illustrato l'utilizzo di questi valori.</span><span class="sxs-lookup"><span data-stu-id="494dc-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="494dc-118">Output:</span><span class="sxs-lookup"><span data-stu-id="494dc-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="494dc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="494dc-119">See also</span></span>

- [<span data-ttu-id="494dc-120">Direttive per il compilatore</span><span class="sxs-lookup"><span data-stu-id="494dc-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="494dc-121">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="494dc-121">F# Language Reference</span></span>](index.md)
