---
title: Copiare e aggiornare espressioni di record
description: Informazioni su come scrivere un'espressione di copia e aggiornamento che copia un record esistente o un record Anonimo, aggiorna i campi specificati e restituisce il record aggiornato o il record anonimo.
author: ChrSteinert
ms.date: 06/12/2019
ms.openlocfilehash: dfb20a6ff8282ae5988772cc0f0841db23aad942
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630383"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="412e0-103">Copiare e aggiornare espressioni di record</span><span class="sxs-lookup"><span data-stu-id="412e0-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="412e0-104">Un' *espressione di record di copia e aggiornamento* è un'espressione che copia un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.</span><span class="sxs-lookup"><span data-stu-id="412e0-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="412e0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="412e0-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-labels }

{| anonymous-record-name with
    updated-labels |}
```

## <a name="remarks"></a><span data-ttu-id="412e0-106">Note</span><span class="sxs-lookup"><span data-stu-id="412e0-106">Remarks</span></span>

<span data-ttu-id="412e0-107">I record e i record anonimi non sono modificabili per impostazione predefinita, pertanto non è possibile eseguire l'aggiornamento a un record esistente.</span><span class="sxs-lookup"><span data-stu-id="412e0-107">Records and anonymous records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="412e0-108">Per creare un record aggiornato, è necessario specificare nuovamente tutti i campi di un record.</span><span class="sxs-lookup"><span data-stu-id="412e0-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="412e0-109">Per semplificare questa attività, è possibile utilizzare un' *espressione di copia e aggiornamento* .</span><span class="sxs-lookup"><span data-stu-id="412e0-109">To simplify this task a *copy and update expression* can be used.</span></span> <span data-ttu-id="412e0-110">Questa espressione accetta un record esistente, ne crea uno nuovo dello stesso tipo usando i campi specificati dall'espressione e il campo mancante specificato dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="412e0-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>

<span data-ttu-id="412e0-111">Questa operazione può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori di campo.</span><span class="sxs-lookup"><span data-stu-id="412e0-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="412e0-112">Prendere ad esempio un record appena creato.</span><span class="sxs-lookup"><span data-stu-id="412e0-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="412e0-113">Se si desidera eseguire l'aggiornamento solo sul campo di tale record, è possibile utilizzare l' *espressione di copia e aggiornamento del record* come la seguente:</span><span class="sxs-lookup"><span data-stu-id="412e0-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="412e0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="412e0-114">See also</span></span>

- [<span data-ttu-id="412e0-115">Record</span><span class="sxs-lookup"><span data-stu-id="412e0-115">Records</span></span>](records.md)
- [<span data-ttu-id="412e0-116">Record anonimi</span><span class="sxs-lookup"><span data-stu-id="412e0-116">Anonymous Records</span></span>](anonymous-records.md)
- [<span data-ttu-id="412e0-117">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="412e0-117">F# Language Reference</span></span>](index.md)
