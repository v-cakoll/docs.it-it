---
title: 'Procedura: Passare argomenti a una routine (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
ms.openlocfilehash: 012ad8e6229958575030ee820a3b0b79cc50facc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863441"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Procedura: Passare argomenti a una routine (Visual Basic)
Quando si chiama una routine, si seguono il nome della routine con un elenco di argomenti racchiuso tra parentesi. Viene fornito un argomento corrispondente a ogni parametro obbligatorio, definisce la procedura e, facoltativamente, è possibile specificare argomenti per il `Optional` parametri. Se non si fornisce un `Optional` parametro nella chiamata, è necessario includere una virgola per contrassegnarne la posizione nell'elenco di argomenti, se viene fornito alcun argomento successivo.  
  
 Se si prevede di passare un argomento di un tipo di dati diverso da quello del parametro corrispondente, ad esempio `Byte` al `String`, è possibile impostare l'opzione di controllo del tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) per `Off`. Se `Option Strict` è `On`, è necessario utilizzare parole chiave di conversione esplicita o le conversioni di ampliamento. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e [funzioni di conversione del tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Per altre informazioni, vedere [parametri delle Procedure e argomenti](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Per passare uno o più argomenti a una routine  
  
1. Nell'istruzione di chiamata, inserire il nome della routine tra parentesi.  
  
2. All'interno delle parentesi, inserire un elenco di argomenti. Includere un argomento per ogni parametro obbligatorio, che definisce la routine e gli argomenti, separarli con virgole.  
  
3. Assicurarsi che ogni argomento è un'espressione valida che restituisce un tipo di dati convertibile nel tipo di routine definisce per il parametro corrispondente.  
  
4. Se un parametro viene definito come [facoltativo](../../../../visual-basic/language-reference/modifiers/optional.md), è possibile includerlo nell'elenco di argomenti oppure ometterlo. Se viene omesso, la routine utilizza il valore predefinito definito per tale parametro.  
  
5. Se si omette un argomento per un `Optional` parametro ed è presente un altro parametro dopo di esso nell'elenco dei parametri, è possibile contrassegnare la posizione dell'argomento omesso da una virgola aggiuntiva nell'elenco di argomenti.  
  
     L'esempio seguente chiama il Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> (funzione).  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     Nell'esempio precedente specifica il primo argomento obbligatorio, ovvero la stringa di messaggio da visualizzare. Omette un argomento per il secondo parametro facoltativo che specifica i pulsanti da visualizzare nella finestra di messaggio. Poiché la chiamata non fornisce alcun valore, `MsgBox` Usa il valore predefinito `MsgBoxStyle.OKOnly`, che consente di visualizzare solo un **OK** pulsante.  
  
     La seconda virgola nell'elenco di argomenti contrassegna la posizione del secondo argomento viene omesso e l'ultima stringa viene passata al terzo parametro facoltativo di `MsgBox`, ovvero il testo da visualizzare nella barra del titolo.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Procedura: Definire un parametro per una routine](./how-to-define-a-parameter-for-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Routine ricorsive](./recursive-procedures.md)
- [Overload della routine](./procedure-overloading.md)
- [Oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)
