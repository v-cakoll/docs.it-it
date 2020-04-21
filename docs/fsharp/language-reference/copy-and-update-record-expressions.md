---
title: Copiare e aggiornare espressioni di record
description: Informazioni su come scrivere un'espressione di copia e aggiornamento che copia un record esistente o anonimo, aggiorna i campi specificati e restituisce il record aggiornato o anonimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: bec3e0ac2fb34e358b199c509c4599b55d7bf35e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739282"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="e6df4-103">Copiare e aggiornare espressioni di record</span><span class="sxs-lookup"><span data-stu-id="e6df4-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="e6df4-104">Un'espressione di record di *copia e aggiornamento* è un'espressione che copia un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.</span><span class="sxs-lookup"><span data-stu-id="e6df4-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6df4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6df4-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="e6df4-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e6df4-106">Remarks</span></span>

<span data-ttu-id="e6df4-107">I record e i record anonimi non sono modificabili per impostazione predefinita, pertanto non è possibile aggiornare un record esistente.</span><span class="sxs-lookup"><span data-stu-id="e6df4-107">Records and anonymous records are immutable by default, so it is not possible to update an existing record.</span></span> <span data-ttu-id="e6df4-108">Per creare un record aggiornato, è necessario specificare nuovamente tutti i campi di un record.</span><span class="sxs-lookup"><span data-stu-id="e6df4-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="e6df4-109">Per semplificare questa attività è possibile utilizzare *un'espressione* di copia e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e6df4-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="e6df4-110">Questa espressione accetta un record esistente, ne crea uno nuovo dello stesso tipo utilizzando i campi specificati dall'espressione e il campo mancante specificato dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="e6df4-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="e6df4-111">Ciò può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="e6df4-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="e6df4-112">Si crei, ad esempio, un record appena creato.</span><span class="sxs-lookup"><span data-stu-id="e6df4-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="e6df4-113">Per aggiornare solo due campi in tale record è possibile utilizzare l'espressione di *copia e aggiornamento del record:*</span><span class="sxs-lookup"><span data-stu-id="e6df4-113">To update only two fields in that record you can use the *copy and update record expression*:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="e6df4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6df4-114">See also</span></span>

- [<span data-ttu-id="e6df4-115">Record</span><span class="sxs-lookup"><span data-stu-id="e6df4-115">Records</span></span>](records.md)
- [<span data-ttu-id="e6df4-116">Record anonimi</span><span class="sxs-lookup"><span data-stu-id="e6df4-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="e6df4-117">Guida di riferimento al linguaggio F</span><span class="sxs-lookup"><span data-stu-id="e6df4-117">F# Language Reference</span></span>](index.md)
