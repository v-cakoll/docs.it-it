---
title: 'Copia e aggiorna le espressioni del Record (F #)'
description: Informazioni su come scrivere un 'copia e aggiornamento record expression' che consente di copiare un esistente gli aggiornamenti dei record, campi specificati e restituisce il record aggiornato.
author: ChrSteinert
ms.author: phcart
ms.date: 06/04/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 98a515b5f053e9339588157185848e8315a580f4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="05274-103">Copiare e aggiornare espressioni di record</span><span class="sxs-lookup"><span data-stu-id="05274-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="05274-104">Oggetto *espressione record copia e aggiornamento* è un'espressione che consente di copiare un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.</span><span class="sxs-lookup"><span data-stu-id="05274-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>


## <a name="syntax"></a><span data-ttu-id="05274-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05274-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="05274-106">Note</span><span class="sxs-lookup"><span data-stu-id="05274-106">Remarks</span></span>
<span data-ttu-id="05274-107">Record non sono modificabili per impostazione predefinita, in modo che non sia possibile alcun aggiornamento a un record esistente.</span><span class="sxs-lookup"><span data-stu-id="05274-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="05274-108">Per creare un record aggiornato tutti i campi di un record dovranno essere specificato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="05274-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="05274-109">Per semplificare questa attività una *espressione record copia e aggiornamento* può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="05274-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="05274-110">Questa espressione accetta un record esistente, crea una nuova istanza dello stesso tipo con campi specificati dall'espressione e il campo mancante specificati dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="05274-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="05274-111">Può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="05274-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="05274-112">Prendere ad esempio un record appena creato.</span><span class="sxs-lookup"><span data-stu-id="05274-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="05274-113">Se si esegue l'aggiornamento solo su campo di tale record è possibile utilizzare il *espressione record copia e aggiornamento* simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="05274-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="05274-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05274-114">See Also</span></span>
[<span data-ttu-id="05274-115">Record</span><span class="sxs-lookup"><span data-stu-id="05274-115">Records</span></span>](records.md)

[<span data-ttu-id="05274-116">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="05274-116">F# Language Reference</span></span>](index.md)
