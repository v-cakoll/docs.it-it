---
title: Sub (routine)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: 9ca1d302a0bc8e989e0b2dddf8cce68e89211d57
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163813"
---
# <a name="sub-procedures-visual-basic"></a>Procedure secondarie (Visual Basic)

Una `Sub` routine è una serie di istruzioni Visual Basic racchiuse tra le istruzioni `Sub` e `End Sub`. La procedura `Sub` esegue un'attività e quindi restituisce il controllo al codice chiamante, ma non restituisce un valore al codice chiamante.

Ogni volta che viene chiamata la stored procedure, le istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo l'istruzione `Sub` e terminando con la prima istruzione `End Sub`, `Exit Sub`o `Return` rilevata.

È possibile definire una procedura di `Sub` in moduli, classi e strutture. Per impostazione predefinita, è `Public`, quindi è possibile chiamarlo da qualsiasi punto dell'applicazione che abbia accesso al modulo, alla classe o alla struttura in cui è stato definito. Il termine *Metodo* descrive un `Sub` o `Function` routine a cui si accede dall'esterno del modulo, della classe o della struttura che lo definisce. Per altre informazioni, vedere [Routine](./index.md).

Una procedura `Sub` può assumere argomenti, ad esempio costanti, variabili o espressioni, che vengono passati al codice chiamante.

## <a name="declaration-syntax"></a>Sintassi di dichiarazione

La sintassi per la dichiarazione di una procedura `Sub` è la seguente:

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

Il `modifiers` può specificare il livello di accesso e le informazioni sull'overload, l'override, la condivisione e l'ombreggiatura. Per ulteriori informazioni, vedere [istruzione secondaria](../../../language-reference/statements/sub-statement.md).

## <a name="parameter-declaration"></a>Dichiarazione di parametro

Dichiarare ogni parametro di routine in modo analogo a come si dichiara una variabile, specificando il nome del parametro e il tipo di dati. È anche possibile specificare il meccanismo di passaggio e se il parametro è facoltativo o una matrice di parametri.

La sintassi per ogni parametro nell'elenco di parametri è la seguente:

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione. La sintassi per specificare un valore predefinito è la seguente:

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a>Parametri come variabili locali

Quando il controllo passa alla routine, ogni parametro viene considerato come variabile locale. Ciò significa che la durata è identica a quella della procedura e il suo ambito è l'intera routine.

## <a name="calling-syntax"></a>Sintassi di chiamata

Si richiama in modo esplicito una routine di `Sub` con un'istruzione di chiamata autonoma. Non è possibile chiamarlo utilizzandone il nome in un'espressione. È necessario fornire i valori per tutti gli argomenti non facoltativi ed è necessario racchiudere l'elenco di argomenti tra parentesi. Se non viene fornito alcun argomento, facoltativamente è possibile omettere le parentesi. L'uso della parola chiave `Call` è facoltativo ma non consigliato.

La sintassi per una chiamata a una procedura `Sub` è la seguente:

```vb
[Call] SubName[(argumentlist)]
```

È possibile chiamare un metodo di `Sub` dall'esterno della classe che lo definisce. Prima di tutto, è necessario usare la parola chiave `New` per creare un'istanza della classe o chiamare un metodo che restituisce un'istanza della classe. Per ulteriori informazioni, vedere [operatore New](../../../language-reference/operators/new-operator.md). Quindi, è possibile utilizzare la sintassi seguente per chiamare il metodo `Sub` sull'oggetto istanza:

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a>Illustrazione della dichiarazione e della chiamata

La seguente procedura `Sub` indica all'operatore computer l'attività che l'applicazione sta per eseguire e visualizza anche un timestamp. Anziché duplicare questo codice all'inizio di ogni attività, l'applicazione chiama solo `tellOperator` da diverse posizioni. Ogni chiamata passa una stringa nell'argomento `task` che identifica l'attività avviata.

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

Nell'esempio seguente viene illustrata una tipica chiamata a `tellOperator`.

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Sub](../../../language-reference/statements/sub-statement.md)
- [Procedura: Chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [Procedura: chiamare un gestore eventi in Visual Basic](./how-to-call-an-event-handler.md)
