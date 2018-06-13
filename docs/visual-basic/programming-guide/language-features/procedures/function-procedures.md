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
ms.openlocfilehash: 887c930cb757b012542c97d64a57a62882a2eed3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655535"
---
# <a name="function-procedures-visual-basic"></a>Routine Function (Visual Basic)
Un `Function` stored procedure è una serie di istruzioni di Visual Basic racchiuse tra il `Function` e `End Function` istruzioni. Il `Function` routine esegue un'attività e quindi restituisce il controllo al codice chiamante. Quando restituisce il controllo, restituisce inoltre un valore al codice chiamante.  
  
 Ogni volta che la routine viene chiamata, le relative istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo il `Function` istruzione e terminando con il primo `End Function`, `Exit Function`, o `Return` rilevata istruzione.  
  
 È possibile definire un `Function` procedura in un modulo, classe o struttura. È `Public` per impostazione predefinita, il che significa è possibile chiamare da qualsiasi posizione nell'applicazione che ha accesso al modulo, classe o struttura in cui è stata definita.  
  
 Oggetto `Function` procedure può accettare argomenti, ad esempio costanti, variabili o espressioni, che vengono passate al metodo dal codice chiamante.  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 La sintassi per dichiarare un `Function` procedura è la seguente:  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 Il *modificatori* può specificare il livello di accesso e le informazioni su overload, override, condivisione e shadowing. Per ulteriori informazioni, vedere [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Ciascun parametro viene dichiarato esattamente come avviene per [Sub (routine)](./sub-procedures.md).  
  
### <a name="data-type"></a>Tipo di dati  
 Ogni `Function` routine ha un tipo di dati, solo ogni variabile. Questo tipo di dati è specificato mediante il `As` clausola il `Function` istruzione e determina il tipo di dati del valore restituito dalla funzione al codice chiamante. Le dichiarazioni di esempio seguente viene illustrato questo.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 Per ulteriori informazioni, vedere "Parti" in [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="returning-values"></a>Restituzione di valori  
 Il valore di un `Function` procedure invia back al codice chiamante viene chiamato il relativo valore restituito. La procedura restituisce questo valore in uno dei due modi:  
  
-   Usa il `Return` istruzione per specificare il valore restituito e restituisce il controllo immediatamente al programma chiamante. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   Assegna un valore per il proprio nome di funzione in una o più istruzioni della procedura. Il controllo viene restituito al programma chiamante finché un `Exit Function` o `End Function` viene eseguita un'istruzione. Questa condizione è illustrata nell'esempio seguente.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 Il vantaggio dell'assegnazione del valore restituito per il nome della funzione è che il controllo viene restituito dalla routine finché incontra un `Exit Function` o `End Function` istruzione. Ciò consente di assegnare un valore preliminare e modificarlo in un secondo momento se necessario.  
  
 Per ulteriori informazioni sulla restituzione di valori, vedere [istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md). Per informazioni sulla restituzione di matrici, vedere [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="calling-syntax"></a>Sintassi di chiamata  
 Si richiama un `Function` procedura includendo il nome e gli argomenti sul lato destro di un'istruzione di assegnazione o in un'espressione. È necessario fornire valori per tutti gli argomenti che non sono facoltativi e, è necessario racchiudere l'elenco di argomenti tra parentesi. Se non vengono forniti argomenti, è possibile omettere le parentesi.  
  
 La sintassi per una chiamata a un `Function` procedura è la seguente:  
  
 *lvalue*`=`*functionname* `[(` *argumentlist*  `)]`  
  
 `If ((` *nomefunzione* `[(` *argumentlist* `)] / 3) <=` *espressione*  `) Then`  
  
 Quando si chiama un `Function` routine, non è necessario utilizzare il valore restituito. In caso contrario, vengono eseguite tutte le azioni della funzione, ma il valore restituito viene ignorato. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> è spesso definito in questo modo.  
  
### <a name="illustration-of-declaration-and-call"></a>Illustrazione di dichiarazione e chiamata  
 Le operazioni seguenti `Function` procedure calcola il lato più lungo, ovvero l'ipotenusa, di un triangolo rettangolo, in base ai valori per i due lati.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 Nell'esempio seguente viene illustrata una tipica chiamata a `hypotenuse`.  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Sub](./sub-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Function](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Procedura: Creare una routine che restituisce un valore](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Procedura: Restituire un valore da una routine](./how-to-return-a-value-from-a-procedure.md)  
 [Procedura: Chiamare una routine che restituisce un valore](./how-to-call-a-procedure-that-returns-a-value.md)
