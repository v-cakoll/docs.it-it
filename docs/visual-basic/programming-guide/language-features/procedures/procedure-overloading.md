---
title: Overload della routine
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 41a971896fe726cbe9849fd46334910e7288afe0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352592"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="1e92b-102">Overload della routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e92b-102">Procedure Overloading (Visual Basic)</span></span>

<span data-ttu-id="1e92b-103">L' *Overload* di una routine significa definendolo in più versioni, usando lo stesso nome ma elenchi di parametri diversi.</span><span class="sxs-lookup"><span data-stu-id="1e92b-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="1e92b-104">Lo scopo dell'overload è definire diverse versioni strettamente correlate di una stored procedure senza doverle differenziare per nome.</span><span class="sxs-lookup"><span data-stu-id="1e92b-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="1e92b-105">A tale scopo, variare l'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="1e92b-105">You do this by varying the parameter list.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="1e92b-106">Overload di regole</span><span class="sxs-lookup"><span data-stu-id="1e92b-106">Overloading Rules</span></span>

<span data-ttu-id="1e92b-107">Quando si esegue l'overload di una stored procedure, si applicano le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e92b-107">When you overload a procedure, the following rules apply:</span></span>

- <span data-ttu-id="1e92b-108">**Lo stesso nome**.</span><span class="sxs-lookup"><span data-stu-id="1e92b-108">**Same Name**.</span></span> <span data-ttu-id="1e92b-109">Ogni versione di overload deve utilizzare lo stesso nome di procedura.</span><span class="sxs-lookup"><span data-stu-id="1e92b-109">Each overloaded version must use the same procedure name.</span></span>

- <span data-ttu-id="1e92b-110">**Firma diversa**.</span><span class="sxs-lookup"><span data-stu-id="1e92b-110">**Different Signature**.</span></span> <span data-ttu-id="1e92b-111">Ogni versione di overload deve essere diversa da tutte le altre versioni di overload in almeno uno dei seguenti aspetti:</span><span class="sxs-lookup"><span data-stu-id="1e92b-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>

  - <span data-ttu-id="1e92b-112">Numero di parametri</span><span class="sxs-lookup"><span data-stu-id="1e92b-112">Number of parameters</span></span>

  - <span data-ttu-id="1e92b-113">Ordine dei parametri</span><span class="sxs-lookup"><span data-stu-id="1e92b-113">Order of the parameters</span></span>

  - <span data-ttu-id="1e92b-114">Tipi di dati dei parametri</span><span class="sxs-lookup"><span data-stu-id="1e92b-114">Data types of the parameters</span></span>

  - <span data-ttu-id="1e92b-115">Numero di parametri di tipo (per una routine generica)</span><span class="sxs-lookup"><span data-stu-id="1e92b-115">Number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="1e92b-116">Tipo restituito (solo per un operatore di conversione)</span><span class="sxs-lookup"><span data-stu-id="1e92b-116">Return type (only for a conversion operator)</span></span>

  <span data-ttu-id="1e92b-117">Insieme al nome della procedura, gli elementi precedenti sono collettivamente chiamati *firma* della procedura.</span><span class="sxs-lookup"><span data-stu-id="1e92b-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="1e92b-118">Quando si chiama una routine di overload, il compilatore usa la firma per verificare che la chiamata corrisponda correttamente alla definizione.</span><span class="sxs-lookup"><span data-stu-id="1e92b-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>

- <span data-ttu-id="1e92b-119">**Elementi che non fanno parte della firma**.</span><span class="sxs-lookup"><span data-stu-id="1e92b-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="1e92b-120">Non è possibile eseguire l'overload di una routine senza variare la firma.</span><span class="sxs-lookup"><span data-stu-id="1e92b-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="1e92b-121">In particolare, non è possibile eseguire l'overload di una routine variando solo uno o più degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e92b-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>

  - <span data-ttu-id="1e92b-122">Parole chiave del modificatore di routine, ad esempio `Public`, `Shared`e `Static`</span><span class="sxs-lookup"><span data-stu-id="1e92b-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>

  - <span data-ttu-id="1e92b-123">Parametri o nomi dei parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="1e92b-123">Parameter or type parameter names</span></span>

  - <span data-ttu-id="1e92b-124">Vincoli del parametro di tipo (per una routine generica)</span><span class="sxs-lookup"><span data-stu-id="1e92b-124">Type parameter constraints (for a generic procedure)</span></span>

  - <span data-ttu-id="1e92b-125">Parole chiave del modificatore di parametro, ad esempio `ByRef` e `Optional`</span><span class="sxs-lookup"><span data-stu-id="1e92b-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>

  - <span data-ttu-id="1e92b-126">Indica se restituisce un valore</span><span class="sxs-lookup"><span data-stu-id="1e92b-126">Whether it returns a value</span></span>

  - <span data-ttu-id="1e92b-127">Tipo di dati del valore restituito (ad eccezione di un operatore di conversione)</span><span class="sxs-lookup"><span data-stu-id="1e92b-127">The data type of the return value (except for a conversion operator)</span></span>

  <span data-ttu-id="1e92b-128">Gli elementi nell'elenco precedente non fanno parte della firma.</span><span class="sxs-lookup"><span data-stu-id="1e92b-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="1e92b-129">Sebbene non sia possibile utilizzarli per distinguere le versioni di overload, è possibile variare tra le versioni di overload che sono correttamente differenziate in base alle rispettive firme.</span><span class="sxs-lookup"><span data-stu-id="1e92b-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>

- <span data-ttu-id="1e92b-130">**Argomenti ad associazione tardiva**.</span><span class="sxs-lookup"><span data-stu-id="1e92b-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="1e92b-131">Se si intende passare una variabile oggetto con associazione tardiva a una versione di overload, è necessario dichiarare il parametro appropriato come <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="1e92b-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>

## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="1e92b-132">Più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="1e92b-132">Multiple Versions of a Procedure</span></span>

<span data-ttu-id="1e92b-133">Si supponga di scrivere una procedura `Sub` per pubblicare una transazione rispetto al saldo del cliente e di voler fare riferimento al cliente in base al nome o al numero di conto.</span><span class="sxs-lookup"><span data-stu-id="1e92b-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="1e92b-134">Per risolvere questo problema, è possibile definire due diverse `Sub` procedure, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1e92b-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a><span data-ttu-id="1e92b-135">Versioni di overload</span><span class="sxs-lookup"><span data-stu-id="1e92b-135">Overloaded Versions</span></span>

<span data-ttu-id="1e92b-136">In alternativa, è possibile eseguire l'overload di un singolo nome di procedura.</span><span class="sxs-lookup"><span data-stu-id="1e92b-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="1e92b-137">È possibile usare la parola chiave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) per definire una versione della routine per ogni elenco di parametri, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1e92b-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a><span data-ttu-id="1e92b-138">Overload aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="1e92b-138">Additional Overloads</span></span>

<span data-ttu-id="1e92b-139">Se si desidera accettare anche un importo di transazione in `Decimal` o `Single`, è possibile eseguire ulteriori Overload `post` per consentire questa variazione.</span><span class="sxs-lookup"><span data-stu-id="1e92b-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="1e92b-140">Se questa operazione è stata apportata a ognuno degli overload dell'esempio precedente, si avranno quattro `Sub` procedure, tutte con lo stesso nome ma con quattro firme diverse.</span><span class="sxs-lookup"><span data-stu-id="1e92b-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>

## <a name="advantages-of-overloading"></a><span data-ttu-id="1e92b-141">Vantaggi dell'overload</span><span class="sxs-lookup"><span data-stu-id="1e92b-141">Advantages of Overloading</span></span>

<span data-ttu-id="1e92b-142">Il vantaggio dell'overload di una stored procedure è la flessibilità della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e92b-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="1e92b-143">Per utilizzare la procedura `post` dichiarata nell'esempio precedente, il codice chiamante può ottenere l'identificazione del cliente come `String` o `Integer`, quindi chiamare la stessa procedura in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="1e92b-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="1e92b-144">Questa condizione è illustrata nell'esempio che segue.</span><span class="sxs-lookup"><span data-stu-id="1e92b-144">The following example illustrates this:</span></span>

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a><span data-ttu-id="1e92b-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e92b-145">See also</span></span>

- [<span data-ttu-id="1e92b-146">Routine</span><span class="sxs-lookup"><span data-stu-id="1e92b-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1e92b-147">Procedura: Definire più versioni di una routine</span><span class="sxs-lookup"><span data-stu-id="1e92b-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="1e92b-148">Procedura: Chiamare una routine di overload</span><span class="sxs-lookup"><span data-stu-id="1e92b-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="1e92b-149">Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="1e92b-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="1e92b-150">Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri</span><span class="sxs-lookup"><span data-stu-id="1e92b-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="1e92b-151">Considerazioni sull'overload di routine</span><span class="sxs-lookup"><span data-stu-id="1e92b-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="1e92b-152">Risoluzione dell'overload</span><span class="sxs-lookup"><span data-stu-id="1e92b-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="1e92b-153">Overloads</span><span class="sxs-lookup"><span data-stu-id="1e92b-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="1e92b-154">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e92b-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
