---
title: 'Procedura: passare argomenti a una routine'
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
ms.openlocfilehash: 903e05facccd1f2afdf4bb51b200531feb64aa79
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387777"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Procedura: passare argomenti a una routine (Visual Basic)
Quando si chiama una routine, il nome della procedura viene seguito da un elenco di argomenti racchiuso tra parentesi. Si fornisce un argomento corrispondente a ogni parametro obbligatorio definito dalla procedura ed è possibile specificare facoltativamente argomenti per i `Optional` parametri. Se non si specifica un `Optional` parametro nella chiamata, è necessario includere una virgola per contrassegnare la posizione nell'elenco di argomenti se si specificano gli argomenti successivi.  
  
 Se si intende passare un argomento di un tipo di dati diverso da quello del parametro corrispondente, ad esempio `Byte` a `String` , è possibile impostare l'opzione di controllo del tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) su `Off` . Se `Option Strict` è `On` , è necessario usare le conversioni verso un tipo di conversione più ampio o le parole chiave di conversione esplicita. Per altre informazioni, vedere [conversioni](../data-types/widening-and-narrowing-conversions.md) verso un tipo di dati più piccolo e le [funzioni di conversione dei tipi](../../../language-reference/functions/type-conversion-functions.md).  
  
 Per ulteriori informazioni, vedere [parametri e argomenti delle procedure](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Per passare uno o più argomenti a una routine  
  
1. Nell'istruzione chiamante, seguire il nome della procedura con le parentesi.  
  
2. Inserire un elenco di argomenti all'interno delle parentesi. Includere un argomento per ogni parametro obbligatorio definito dalla procedura e separare gli argomenti con virgole.  
  
3. Verificare che ogni argomento sia un'espressione valida che restituisca un tipo di dati convertibile nel tipo definito dalla routine per il parametro corrispondente.  
  
4. Se un parametro è definito come [facoltativo](../../../language-reference/modifiers/optional.md), è possibile includerlo nell'elenco di argomenti o ometterlo. Se la si omette, la procedura utilizzerà il valore predefinito definito per il parametro.  
  
5. Se si omette un argomento per un `Optional` parametro ed è presente un altro parametro dopo di esso nell'elenco dei parametri, è possibile contrassegnare la posizione dell'argomento omesso con una virgola aggiuntiva nell'elenco di argomenti.  
  
     Nell'esempio seguente viene chiamata la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> funzione Visual Basic.  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     Nell'esempio precedente viene fornito il primo argomento obbligatorio, ovvero la stringa di messaggio da visualizzare. Omette un argomento per il secondo parametro facoltativo, che specifica i pulsanti da visualizzare nella finestra di messaggio. Poiché la chiamata non fornisce un valore, in `MsgBox` viene utilizzato il valore predefinito, `MsgBoxStyle.OKOnly` , che visualizza solo un pulsante **OK** .  
  
     La seconda virgola nell'elenco di argomenti contrassegna il posto del secondo argomento omesso e l'ultima stringa viene passata al terzo parametro facoltativo di `MsgBox` , ovvero il testo da visualizzare nella barra del titolo.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Sub](./sub-procedures.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Procedura: definire un parametro per una routine](./how-to-define-a-parameter-for-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Routine ricorsive](./recursive-procedures.md)
- [Overload della routine](./procedure-overloading.md)
- [Oggetti e classi](../objects-and-classes/index.md)
- [Programmazione orientata a oggetti (Visual Basic)](../../concepts/object-oriented-programming.md)
