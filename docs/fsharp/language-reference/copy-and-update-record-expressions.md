---
title: 'Copia e aggiorna le espressioni del Record (F #)'
description: Informazioni su come scrivere un 'copia e aggiornamento record expression' che consente di copiare un esistente gli aggiornamenti dei record, campi specificati e restituisce il record aggiornato.
keywords: visual f#, f#, programmazione funzionale
author: ChrSteinert
ms.author: phcart
ms.date: 06/04/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b5fc4ef0-64eb-4272-96a7-bb4dffbb634a
ms.openlocfilehash: 2eb51842b678780a1d6da96e237ebb92d1ea5cec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="ed0a0-104">Copiare e aggiornare espressioni di record</span><span class="sxs-lookup"><span data-stu-id="ed0a0-104">Copy and Update Record Expressions</span></span>

<span data-ttu-id="ed0a0-105">Oggetto *espressione record copia e aggiornamento* è un'espressione che consente di copiare un record esistente, aggiorna i campi specificati e restituisce il record aggiornato.</span><span class="sxs-lookup"><span data-stu-id="ed0a0-105">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>


## <a name="syntax"></a><span data-ttu-id="ed0a0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed0a0-106">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="ed0a0-107">Note</span><span class="sxs-lookup"><span data-stu-id="ed0a0-107">Remarks</span></span>
<span data-ttu-id="ed0a0-108">Record non sono modificabili per impostazione predefinita, in modo che non sia possibile alcun aggiornamento a un record esistente.</span><span class="sxs-lookup"><span data-stu-id="ed0a0-108">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="ed0a0-109">Per creare un record aggiornato tutti i campi di un record dovranno essere specificato nuovamente.</span><span class="sxs-lookup"><span data-stu-id="ed0a0-109">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="ed0a0-110">Per semplificare questa attività una *espressione record copia e aggiornamento* può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ed0a0-110">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="ed0a0-111">Questa espressione accetta un record esistente, crea una nuova istanza dello stesso tipo con campi specificati dall'espressione e il campo mancante specificati dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="ed0a0-111">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="ed0a0-112">Può essere utile quando è necessario copiare un record esistente ed eventualmente modificare alcuni dei valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="ed0a0-112">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="ed0a0-113">Prendere ad esempio un record appena creato.</span><span class="sxs-lookup"><span data-stu-id="ed0a0-113">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="ed0a0-114">Se si esegue l'aggiornamento solo su campo di tale record è possibile utilizzare il *espressione record copia e aggiornamento* simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="ed0a0-114">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="ed0a0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed0a0-115">See Also</span></span>
[<span data-ttu-id="ed0a0-116">Record</span><span class="sxs-lookup"><span data-stu-id="ed0a0-116">Records</span></span>](records.md)

[<span data-ttu-id="ed0a0-117">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="ed0a0-117">F# Language Reference</span></span>](index.md)
