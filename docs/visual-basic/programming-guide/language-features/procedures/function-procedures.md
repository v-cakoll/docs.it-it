---
title: routine di Function
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: d7a0293e2ec520c2278f67156be56315d1def2b5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76780086"
---
# <a name="function-procedures-visual-basic"></a>Routine Function (Visual Basic)

Una `Function` routine è una serie di istruzioni Visual Basic racchiuse tra le istruzioni `Function` e `End Function`. La procedura `Function` esegue un'attività e quindi restituisce il controllo al codice chiamante. Quando restituisce il controllo, restituisce anche un valore al codice chiamante.

Ogni volta che viene chiamata la stored procedure, le istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo l'istruzione `Function` e terminando con la prima istruzione `End Function`, `Exit Function`o `Return` rilevata.

È possibile definire una procedura di `Function` in un modulo, una classe o una struttura. È `Public` per impostazione predefinita, il che significa che è possibile chiamarlo da qualsiasi punto dell'applicazione che abbia accesso al modulo, alla classe o alla struttura in cui è stato definito.

Una procedura `Function` può assumere argomenti, ad esempio costanti, variabili o espressioni, che vengono passati al codice chiamante.

## <a name="declaration-syntax"></a>Sintassi di dichiarazione

La sintassi per la dichiarazione di una procedura `Function` è la seguente:

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

I *modificatori* possono specificare il livello di accesso e le informazioni relative all'overload, all'override, alla condivisione e all'ombreggiatura. Per ulteriori informazioni, vedere [istruzione Function](../../../language-reference/statements/function-statement.md).

Ogni parametro viene dichiarato in modo analogo alle [procedure secondarie](./sub-procedures.md).

### <a name="data-type"></a>Tipo di dati

Ogni `Function` routine ha un tipo di dati, proprio come ogni variabile. Questo tipo di dati viene specificato dalla clausola `As` nell'istruzione `Function` e determina il tipo di dati del valore restituito dalla funzione al codice chiamante. Questa operazione viene illustrata nelle dichiarazioni di esempio seguenti.

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

Per ulteriori informazioni, vedere l'argomento relativo alle parti nell' [istruzione Function](../../../language-reference/statements/function-statement.md).

### <a name="returning-values"></a>Restituzione di valori

Il valore restituito da una procedura `Function` al codice chiamante viene chiamato valore restituito. La procedura restituisce questo valore in uno dei due modi seguenti:

- Usa l'istruzione `Return` per specificare il valore restituito e restituisce immediatamente il controllo al programma chiamante. Ciò è illustrato nell'esempio seguente.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- Assegna un valore al relativo nome di funzione in una o più istruzioni della procedura. Il controllo non torna al programma chiamante finché non viene eseguita un'istruzione `Exit Function` o `End Function`. Ciò è illustrato nell'esempio seguente.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

Il vantaggio derivante dall'assegnazione del valore restituito al nome della funzione è che il controllo non restituisce dalla procedura fino a quando non rileva un'istruzione `Exit Function` o `End Function`. In questo modo è possibile assegnare un valore preliminare e modificarlo in un secondo momento, se necessario.

Per ulteriori informazioni sulla restituzione di valori, vedere [istruzione Function](../../../language-reference/statements/function-statement.md). Per informazioni sulla restituzione di matrici, vedere [matrici](../arrays/index.md).

## <a name="calling-syntax"></a>Sintassi di chiamata

Si richiama una procedura di `Function` includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione. È necessario fornire i valori per tutti gli argomenti non facoltativi ed è necessario racchiudere l'elenco di argomenti tra parentesi. Se non viene fornito alcun argomento, facoltativamente è possibile omettere le parentesi.

Di seguito è riportata la sintassi per una chiamata a una procedura `Function`.

*lvalue*`=`*FunctionName* `[(` *argomento* `)]`

`If ((` *functionname* `[(` l' *argomento* `)] / 3) <=`*espressione* `) Then`

Quando si chiama una routine di `Function`, non è necessario usare il relativo valore restituito. In caso contrario, vengono eseguite tutte le azioni della funzione, ma il valore restituito viene ignorato. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> viene spesso chiamato in questo modo.

### <a name="illustration-of-declaration-and-call"></a>Illustrazione della dichiarazione e della chiamata

La seguente procedura `Function` calcola il lato più lungo, o ipotenusa, di un triangolo rettangolo, dati i valori per gli altri due lati.

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`.

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Procedura: Creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md)
- [Procedura: Restituire un valore da una routine](./how-to-return-a-value-from-a-procedure.md)
- [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
