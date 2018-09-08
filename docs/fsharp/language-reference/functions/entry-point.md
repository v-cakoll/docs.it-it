---
title: Punto di ingresso (F#)
description: "Informazioni su come impostare il punto di ingresso a un programma F # che viene compilato come file eseguibile, in cui inizia formalmente l'esecuzione."
ms.date: 05/16/2016
ms.openlocfilehash: 298500931d49c891a7a243295333df3a9f5d413e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44189222"
---
# <a name="entry-point"></a><span data-ttu-id="d0554-103">Punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="d0554-103">Entry Point</span></span>

<span data-ttu-id="d0554-104">In questo argomento descrive il metodo utilizzato per impostare il punto di ingresso a un programma F #.</span><span class="sxs-lookup"><span data-stu-id="d0554-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0554-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d0554-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="d0554-106">Note</span><span class="sxs-lookup"><span data-stu-id="d0554-106">Remarks</span></span>

<span data-ttu-id="d0554-107">Nella sintassi precedente, *associazione di funzione let* è la definizione di una funzione in un `let` associazione.</span><span class="sxs-lookup"><span data-stu-id="d0554-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="d0554-108">Il punto di ingresso a un programma che viene compilato come file eseguibile è dove formalmente inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d0554-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="d0554-109">È possibile specificare il punto di ingresso a un'applicazione F # applicando la `EntryPoint` dell'attributo del programma `main` (funzione).</span><span class="sxs-lookup"><span data-stu-id="d0554-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="d0554-110">Questa funzione (creato tramite un `let` associazione) deve essere l'ultima funzione nell'ultimo file compilato.</span><span class="sxs-lookup"><span data-stu-id="d0554-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="d0554-111">L'ultimo file compilato è l'ultimo file nel progetto o l'ultimo file che viene passata alla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d0554-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="d0554-112">La funzione di punto di ingresso ha tipo `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="d0554-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="d0554-113">Gli argomenti specificati nella riga di comando vengono passati al `main` funzione nella matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="d0554-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="d0554-114">Il primo elemento della matrice è il primo argomento. il nome del file eseguibile non è incluso nella matrice, come succede in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="d0554-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="d0554-115">Il valore restituito viene utilizzato come il codice di uscita del processo.</span><span class="sxs-lookup"><span data-stu-id="d0554-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="d0554-116">Zero indica in genere eseguita correttamente. valori diversi da zero indicano un errore.</span><span class="sxs-lookup"><span data-stu-id="d0554-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="d0554-117">Non sono previste convenzioni per il particolare significato dei codici restituiti diversi da zero; il significato dei codici restituiti è specifici dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d0554-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="d0554-118">L'esempio seguente illustra un semplice `main` (funzione).</span><span class="sxs-lookup"><span data-stu-id="d0554-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="d0554-119">Quando viene eseguito questo codice con la riga di comando `EntryPoint.exe 1 2 3`, l'output è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d0554-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="d0554-120">Punto di ingresso impliciti</span><span class="sxs-lookup"><span data-stu-id="d0554-120">Implicit Entry Point</span></span>

<span data-ttu-id="d0554-121">Quando un programma non ha alcun **EntryPoint** attributo che indica in modo esplicito il punto di ingresso, le associazioni di livello superiore nell'ultimo file da compilare sono usati come punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="d0554-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0554-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0554-122">See also</span></span>

- [<span data-ttu-id="d0554-123">Funzioni</span><span class="sxs-lookup"><span data-stu-id="d0554-123">Functions</span></span>](index.md)
- [<span data-ttu-id="d0554-124">Associazioni let</span><span class="sxs-lookup"><span data-stu-id="d0554-124">let Bindings</span></span>](let-bindings.md)
