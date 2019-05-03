---
title: Routine Function (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 568489d6034316e895cd999801241fa995aadefa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864403"
---
# <a name="function-procedures-visual-basic"></a>Routine Function (Visual Basic)
Oggetto `Function` routine è una serie di istruzioni di Visual Basic racchiuse tra il `Function` e `End Function` istruzioni. Il `Function` routine esegue un'attività e quindi restituisce il controllo al codice chiamante. Quando restituisce il controllo, restituisce anche un valore al codice chiamante.  
  
 Ogni volta che la procedura viene chiamata, le relative istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo il `Function` istruzione e terminando con il primo `End Function`, `Exit Function`, o `Return` rilevata istruzione.  
  
 È possibile definire un `Function` procedure in un modulo, classe o struttura. Si tratta di `Public` per impostazione predefinita, il che significa è possibile chiamare da qualsiasi posizione nell'applicazione che dispone dell'accesso per il modulo, classe o struttura in cui è stata definita.  
  
 Oggetto `Function` procedure può accettare argomenti, ad esempio le costanti, variabili o espressioni che vengono passate al metodo dal codice chiamante.  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 La sintassi per dichiarare un `Function` procedura è la seguente:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 Il *modificatori* può specificare il livello di accesso e le informazioni riguardanti l'overload, si esegue l'override, la condivisione e lo shadowing. Per altre informazioni, vedere [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Ogni parametro è dichiarare la stessa procedura valida per [Sub (routine)](./sub-procedures.md).  
  
### <a name="data-type"></a>Tipo di dati  
 Ogni `Function` routine ha un tipo di dati, viene semplicemente tutte le variabili. Questo tipo di dati è specificato mediante il `As` clausola nel `Function` istruzione che determina il tipo di dati del valore che la funzione restituisce al codice chiamante. Le dichiarazioni di esempio seguenti illustrano questo.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Per altre informazioni, vedere "Part" nella [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Restituzione di valori  
 Il valore un `Function` procedure invia informazioni al codice chiamante viene chiamato il relativo valore restituito. La procedura restituisce questo valore in uno dei due modi:  
  
- Usa il `Return` istruzione per specificare il valore restituito e restituisce il controllo immediatamente a nel programma chiamante. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
- Assegna un valore per il proprio nome di funzione in una o più istruzioni della procedura. Il controllo viene restituito al programma chiamante fino a un `Exit Function` o `End Function` viene eseguita un'istruzione. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 Il vantaggio di assegnazione del valore restituito per il nome della funzione è che il controllo viene restituito dalla procedura finché non viene rilevata un' `Exit Function` o `End Function` istruzione. In questo modo è possibile assegnare un valore preliminare e modificarlo in un secondo momento se necessario.  
  
 Per altre informazioni sulla restituzione di valori, vedere [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md). Per informazioni sulla restituzione di matrici, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Sintassi di chiamata  
 Si richiama un `Function` procedura includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione. È necessario fornire valori per tutti gli argomenti che non sono facoltativi e, è necessario racchiudere l'elenco di argomenti racchiuso tra parentesi. Se viene fornito alcun argomento, è possibile omettere le parentesi.  
  
 La sintassi per una chiamata a un `Function` procedura è la seguente:  
  
 *lvalue*`=`*nomefunzione* `[(` *argumentlist* `)]`  
  
 `If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`  
  
 Quando si chiama un `Function` procedura, non è necessario usare il relativo valore restituito. In caso contrario, vengono eseguite tutte le azioni della funzione, ma il valore restituito viene ignorato. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> è spesso definito in questo modo.  
  
### <a name="illustration-of-declaration-and-call"></a>Illustrazione di dichiarazione e di chiamata  
 Nell'esempio `Function` procedure calcola il lato lungo, ovvero l'ipotenusa di un triangolo rettangolo, in base ai valori degli altri due lati.  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 Nell'esempio seguente viene illustrata una tipica chiamata alla `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Sub](./sub-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Procedura: Creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md)
- [Procedura: Restituisce il valore da una routine](./how-to-return-a-value-from-a-procedure.md)
- [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
