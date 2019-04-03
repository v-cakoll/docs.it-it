---
title: Routine Sub (Visual Basic)
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
ms.openlocfilehash: b70594e002bbf08f0890586e78df901ccb26c7ce
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843110"
---
# <a name="sub-procedures-visual-basic"></a>Routine Sub (Visual Basic)
Oggetto `Sub` routine è una serie di istruzioni di Visual Basic racchiuse tra il `Sub` e `End Sub` istruzioni. Il `Sub` routine esegue un'attività e quindi restituisce il controllo al codice chiamante, ma non viene restituito un valore al codice chiamante.  
  
 Ogni volta che la procedura viene chiamata, le relative istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo il `Sub` istruzione e terminando con il primo `End Sub`, `Exit Sub`, o `Return` rilevata istruzione.  
  
 È possibile definire un `Sub` procedura in moduli, le classi e strutture. Per impostazione predefinita, questo file è `Public`, ovvero è possibile chiamarlo da qualsiasi posizione nell'applicazione che dispone dell'accesso per il modulo, classe o struttura in cui è stata definita. Il termine *metodo*, viene descritto un `Sub` o `Function` procedure che si accede dall'esterno la definizione di modulo, classe o struttura. Per altre informazioni, vedere [Routine](./index.md).  
  
 Oggetto `Sub` procedure può accettare argomenti, ad esempio le costanti, variabili o espressioni che vengono passate al metodo dal codice chiamante.  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 La sintassi per dichiarare un `Sub` procedura è la seguente:  
  
 `[` *i modificatori* `] Sub` *subname* `[(` *elencoparametri* `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 Il `modifiers` può specificare il livello di accesso e le informazioni su l'overload, si esegue l'override, la condivisione e lo shadowing. Per altre informazioni, vedere [istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="parameter-declaration"></a>Dichiarazione di parametro  
 Ogni parametro di procedura in modo analogo al modo in cui si dichiara una variabile, che specifica il tipo di dati e nome del parametro viene dichiarato. È anche possibile specificare il meccanismo di passaggio e indica se il parametro è facoltativo o una matrice di parametri.  
  
 La sintassi per ogni parametro nell'elenco dei parametri è come segue:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *ParameterName*`As`*datatype*  
  
 Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione. La sintassi per specificare un valore predefinito è come segue:  
  
 `Optional [ByVal | ByRef]`  *ParameterName*`As`*datatype*`=`*defaultvalue*  
  
### <a name="parameters-as-local-variables"></a>Parametri come variabili locali  
 Quando il controllo passa alla procedura, ogni parametro viene considerato come una variabile locale. Ciò significa che la sua durata è uguale a quello della procedura e il relativo ambito è l'intera procedura.  
  
## <a name="calling-syntax"></a>Sintassi di chiamata  
 Si richiama un `Sub` procedure in modo esplicito con un'istruzione di chiamata autonoma. È possibile effettuare la chiamata utilizzando il nome in un'espressione. È necessario fornire valori per tutti gli argomenti che non sono facoltativi e, è necessario racchiudere l'elenco di argomenti racchiuso tra parentesi. Se viene fornito alcun argomento, è possibile omettere le parentesi. L'uso del `Call` la parola chiave è facoltativa, ma non consigliata.  
  
 La sintassi per una chiamata a un `Sub` procedura è la seguente:  
  
 `[Call]`  *subname* `[(` *argumentlist* `)]`  
  
 È possibile chiamare un `Sub` metodo dall'esterno della classe che lo definisce. In primo luogo, è necessario utilizzare il `New` (parola chiave) per creare un'istanza della classe o chiama un metodo che restituisce un'istanza della classe. Per altre informazioni, vedere [operatore New](../../../../visual-basic/language-reference/operators/new-operator.md). Quindi, è possibile usare la sintassi seguente per chiamare il `Sub` metodo sull'oggetto dell'istanza:  
  
 *Oggetto*. *MethodName*`[(`*argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>Illustrazione di dichiarazione e di chiamata  
 Nell'esempio `Sub` procedure indica a quale attività l'applicazione sta per eseguire, l'operatore di computer e visualizza inoltre un timestamp. Anziché ripetere questo codice all'inizio di ogni attività, l'applicazione chiama semplicemente `tellOperator` da diverse posizioni. Ogni chiamata passa una stringa nel `task` argomento che identifica l'attività in corso l'avvio.  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 Nell'esempio seguente viene illustrata una tipica chiamata alla `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Routine Function](./function-procedures.md)
- [Routine Property](./property-procedures.md)
- [Routine di operatore](./operator-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Procedura: Chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [Procedura: Chiamare un gestore eventi in Visual Basic](./how-to-call-an-event-handler.md)
