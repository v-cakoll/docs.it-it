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
ms.openlocfilehash: f8accc74fbdd9b1d8cf9bc3d8f6ddd26f73452b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363876"
---
# <a name="procedure-overloading-visual-basic"></a>Overload della routine (Visual Basic)

L' *Overload* di una routine significa definendolo in più versioni, usando lo stesso nome ma elenchi di parametri diversi. Lo scopo dell'overload è definire diverse versioni strettamente correlate di una stored procedure senza doverle differenziare per nome. A tale scopo, variare l'elenco dei parametri.

## <a name="overloading-rules"></a>Overload di regole

Quando si esegue l'overload di una stored procedure, si applicano le regole seguenti:

- **Lo stesso nome**. Ogni versione di overload deve utilizzare lo stesso nome di procedura.

- **Firma diversa**. Ogni versione di overload deve essere diversa da tutte le altre versioni di overload in almeno uno dei seguenti aspetti:

  - Numero di parametri

  - Ordine dei parametri

  - Tipi di dati dei parametri

  - Numero di parametri di tipo (per una routine generica)

  - Tipo restituito (solo per un operatore di conversione)

  Insieme al nome della procedura, gli elementi precedenti sono collettivamente chiamati *firma* della procedura. Quando si chiama una routine di overload, il compilatore usa la firma per verificare che la chiamata corrisponda correttamente alla definizione.

- **Elementi che non fanno parte della firma**. Non è possibile eseguire l'overload di una routine senza variare la firma. In particolare, non è possibile eseguire l'overload di una routine variando solo uno o più degli elementi seguenti:

  - Parole chiave del modificatore di routine, ad esempio `Public` , `Shared` e`Static`

  - Parametri o nomi dei parametri di tipo

  - Vincoli del parametro di tipo (per una routine generica)

  - Parole chiave del modificatore di parametro, ad esempio `ByRef` e`Optional`

  - Indica se restituisce un valore

  - Tipo di dati del valore restituito (ad eccezione di un operatore di conversione)

  Gli elementi nell'elenco precedente non fanno parte della firma. Sebbene non sia possibile utilizzarli per distinguere le versioni di overload, è possibile variare tra le versioni di overload che sono correttamente differenziate in base alle rispettive firme.

- **Argomenti ad associazione tardiva**. Se si intende passare una variabile oggetto con associazione tardiva a una versione di overload, è necessario dichiarare il parametro appropriato come <xref:System.Object> .

## <a name="multiple-versions-of-a-procedure"></a>Più versioni di una routine

Si supponga di scrivere una `Sub` procedura per pubblicare una transazione rispetto al saldo del cliente e di voler fare riferimento al cliente in base al nome o al numero di conto. Per risolvere questo problema, è possibile definire due diverse `Sub` procedure, come nell'esempio seguente:

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a>Versioni di overload

In alternativa, è possibile eseguire l'overload di un singolo nome di procedura. È possibile usare la parola chiave [Overloads](../../../language-reference/modifiers/overloads.md) per definire una versione della routine per ogni elenco di parametri, come indicato di seguito:

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a>Overload aggiuntivi

Se si desidera accettare anche un importo di transazione in `Decimal` o `Single` , è possibile eseguire un ulteriore overload `post` per consentire questa variazione. Se questa operazione è stata apportata a ognuno degli overload dell'esempio precedente, si avranno quattro `Sub` procedure, tutte con lo stesso nome ma con quattro firme diverse.

## <a name="advantages-of-overloading"></a>Vantaggi dell'overload

Il vantaggio dell'overload di una stored procedure è la flessibilità della chiamata. Per usare la `post` procedura dichiarata nell'esempio precedente, il codice chiamante può ottenere l'identificazione del cliente come `String` o `Integer` , quindi chiamare la stessa procedura in entrambi i casi. L'esempio seguente illustra questi concetti.

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Procedura: definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)
- [Risoluzione dell'overload](./overload-resolution.md)
- [Overload](../../../language-reference/modifiers/overloads.md)
- [Generic Types in Visual Basic](../data-types/generic-types.md)
