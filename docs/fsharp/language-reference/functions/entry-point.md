---
title: Punto di ingresso
description: Informazioni su come impostare il punto di ingresso per F# un programma compilato come file eseguibile, in cui viene avviata formalmente l'esecuzione.
ms.date: 05/16/2016
ms.openlocfilehash: 5e13416131d4dfd22583439fedf51f18f7a461da
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630528"
---
# <a name="entry-point"></a><span data-ttu-id="d3250-103">Punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="d3250-103">Entry Point</span></span>

<span data-ttu-id="d3250-104">In questo argomento viene descritto il metodo utilizzato per impostare il punto di ingresso di F# un programma.</span><span class="sxs-lookup"><span data-stu-id="d3250-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="d3250-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3250-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="d3250-106">Note</span><span class="sxs-lookup"><span data-stu-id="d3250-106">Remarks</span></span>

<span data-ttu-id="d3250-107">Nella sintassi precedente, *let-function-binding* è la definizione di una funzione in un' `let` associazione.</span><span class="sxs-lookup"><span data-stu-id="d3250-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="d3250-108">Il punto di ingresso di un programma compilato come file eseguibile è il punto in cui viene avviata formalmente l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d3250-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="d3250-109">È possibile specificare il punto di ingresso F# a un'applicazione applicando l' `EntryPoint` attributo `main` alla funzione del programma.</span><span class="sxs-lookup"><span data-stu-id="d3250-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="d3250-110">Questa funzione (creata utilizzando un' `let` associazione) deve essere l'ultima funzione nell'ultimo file compilato.</span><span class="sxs-lookup"><span data-stu-id="d3250-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="d3250-111">L'ultimo file compilato è l'ultimo file del progetto o l'ultimo file passato alla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d3250-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="d3250-112">La funzione del punto di ingresso `string array -> int`è di tipo.</span><span class="sxs-lookup"><span data-stu-id="d3250-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="d3250-113">Gli argomenti specificati nella riga di comando vengono passati alla `main` funzione nella matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="d3250-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="d3250-114">Il primo elemento della matrice è il primo argomento; il nome del file eseguibile non è incluso nella matrice, come in altri linguaggi.</span><span class="sxs-lookup"><span data-stu-id="d3250-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="d3250-115">Il valore restituito viene usato come codice di uscita per il processo.</span><span class="sxs-lookup"><span data-stu-id="d3250-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="d3250-116">Zero indica in genere esito positivo. i valori diversi da zero indicano un errore.</span><span class="sxs-lookup"><span data-stu-id="d3250-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="d3250-117">Non esiste alcuna convenzione per il significato specifico di codici restituiti diversi da zero; i significati dei codici restituiti sono specifici dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3250-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="d3250-118">Nell'esempio seguente viene illustrata una `main` funzione semplice.</span><span class="sxs-lookup"><span data-stu-id="d3250-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="d3250-119">Quando questo codice viene eseguito con la riga `EntryPoint.exe 1 2 3`di comando, l'output è il seguente.</span><span class="sxs-lookup"><span data-stu-id="d3250-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="d3250-120">Punto di ingresso implicito</span><span class="sxs-lookup"><span data-stu-id="d3250-120">Implicit Entry Point</span></span>

<span data-ttu-id="d3250-121">Quando un programma non dispone di un attributo **EntryPoint** che indica in modo esplicito il punto di ingresso, le associazioni di primo livello nell'ultimo file da compilare vengono utilizzate come punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="d3250-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3250-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3250-122">See also</span></span>

- [<span data-ttu-id="d3250-123">Funzioni</span><span class="sxs-lookup"><span data-stu-id="d3250-123">Functions</span></span>](index.md)
- [<span data-ttu-id="d3250-124">Associazioni let</span><span class="sxs-lookup"><span data-stu-id="d3250-124">let Bindings</span></span>](let-bindings.md)
