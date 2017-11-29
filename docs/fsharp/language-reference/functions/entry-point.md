---
title: Punto di ingresso (F#)
description: 'Informazioni su come impostare il punto di ingresso per un programma F # che viene compilato come file eseguibile, in cui inizia formalmente l''esecuzione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 91455443-ff9d-4510-a7e9-1560bdcd0bb0
ms.openlocfilehash: 685fd4da67119aa5fcaaffd142a0a17c8f5dc7f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="entry-point"></a><span data-ttu-id="eb5ec-104">Punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="eb5ec-104">Entry Point</span></span>

<span data-ttu-id="eb5ec-105">In questo argomento viene descritto il metodo utilizzato per impostare il punto di ingresso per un programma F #.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-105">This topic describes the method that you use to set the entry point to an F# program.</span></span>


## <a name="syntax"></a><span data-ttu-id="eb5ec-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb5ec-106">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="eb5ec-107">Note</span><span class="sxs-lookup"><span data-stu-id="eb5ec-107">Remarks</span></span>
<span data-ttu-id="eb5ec-108">Nella sintassi precedente, *consentono di associazione di funzione* è la definizione di una funzione in un `let` associazione.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-108">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="eb5ec-109">Il punto di ingresso a un programma che viene compilato come file eseguibile in cui inizia formalmente l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-109">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="eb5ec-110">È possibile specificare il punto di ingresso a un'applicazione di F # applicando il `EntryPoint` attributo per il programma `main` (funzione).</span><span class="sxs-lookup"><span data-stu-id="eb5ec-110">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="eb5ec-111">Questa funzione (creato tramite un `let` associazione) deve essere l'ultima funzione nell'ultimo file compilato.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-111">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="eb5ec-112">L'ultimo file compilato è l'ultimo file nel progetto o l'ultimo file che viene passato alla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-112">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="eb5ec-113">La funzione di punto di ingresso è di tipo `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-113">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="eb5ec-114">Gli argomenti specificati nella riga di comando vengono passati per la `main` funzione nella matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-114">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="eb5ec-115">Il primo elemento della matrice è il primo argomento. il nome del file eseguibile non è incluso nella matrice, come in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-115">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="eb5ec-116">Il valore restituito viene utilizzato come il codice di uscita per il processo.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-116">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="eb5ec-117">Zero indica in genere eseguita correttamente. valori diversi da zero indicano un errore.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-117">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="eb5ec-118">Non sono previste convenzioni per il particolare significato del codice restituito diverso da zero; il significato dei codici restituiti è specifici dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-118">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="eb5ec-119">Nell'esempio seguente viene illustrato un semplice `main` (funzione).</span><span class="sxs-lookup"><span data-stu-id="eb5ec-119">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="eb5ec-120">Quando si esegue questo codice con la riga di comando `EntryPoint.exe 1 2 3`, l'output è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-120">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="eb5ec-121">Punto di ingresso implicito</span><span class="sxs-lookup"><span data-stu-id="eb5ec-121">Implicit Entry Point</span></span>
<span data-ttu-id="eb5ec-122">Quando un programma non ha alcun **EntryPoint** attributo che indica in modo esplicito il punto di ingresso, le associazioni di livello superiore nell'ultimo file da compilare vengono utilizzati come punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="eb5ec-122">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>


## <a name="see-also"></a><span data-ttu-id="eb5ec-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb5ec-123">See Also</span></span>
[<span data-ttu-id="eb5ec-124">Funzioni</span><span class="sxs-lookup"><span data-stu-id="eb5ec-124">Functions</span></span>](index.md)

[<span data-ttu-id="eb5ec-125">Associazioni let</span><span class="sxs-lookup"><span data-stu-id="eb5ec-125">let Bindings</span></span>](let-bindings.md)
