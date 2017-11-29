---
title: Routine Sub (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e20e0dd5ff9e2b931e5792bebb3144930826f89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="sub-procedures-visual-basic"></a>Routine Sub (Visual Basic)
A `Sub` procedure è una serie di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] istruzioni racchiuso il `Sub` e `End Sub` istruzioni. Il `Sub` routine esegue un'attività e quindi restituisce il controllo al codice chiamante, ma non restituisce un valore al codice chiamante.  
  
 Ogni volta che la routine viene chiamata, le relative istruzioni vengono eseguite, a partire dalla prima istruzione eseguibile dopo il `Sub` istruzione e terminando con il primo `End Sub`, `Exit Sub`, o `Return` rilevata istruzione.  
  
 È possibile definire un `Sub` procedura in moduli, classi e strutture. Per impostazione predefinita è `Public`, ovvero è possibile chiamarla da qualsiasi punto dell'applicazione che ha accesso al modulo, classe o struttura in cui è stata definita. Il termine *metodo*, viene descritto un `Sub` o `Function` procedure che si accede dall'esterno la definizione di modulo, classe o struttura. Per altre informazioni, vedere [Routine](./index.md).  
  
 Oggetto `Sub` procedure può accettare argomenti, ad esempio costanti, variabili o espressioni, che vengono passate al metodo dal codice chiamante.  
  
## <a name="declaration-syntax"></a>Sintassi di dichiarazione  
 La sintassi per dichiarare un `Sub` procedura è la seguente:  
  
 `[`*modificatori* `] Sub` *subname* `[(` *elencoparametri*  `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 Il `modifiers` può specificare il livello di accesso e informazioni su overload, override, condivisione e shadowing. Per ulteriori informazioni, vedere [istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="parameter-declaration"></a>Dichiarazione di parametro  
 Dichiarare ogni parametro di routine in modo analogo a come si dichiara una variabile, che specifica il tipo di dati e nome di parametro. È inoltre possibile specificare il meccanismo di passaggio e se il parametro è facoltativo o una matrice di parametri.  
  
 La sintassi per ogni parametro nell'elenco di parametri è come segue:  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *ParameterName*`As`*tipo di dati*   
  
 Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione. La sintassi per specificare un valore predefinito è come segue:  
  
 `Optional [ByVal | ByRef]`  *ParameterName*`As`*datatype*`=`*defaultvalue*   
  
### <a name="parameters-as-local-variables"></a>Parametri come variabili locali  
 Quando il controllo passa alla routine, ogni parametro viene trattato come una variabile locale. Ciò significa che la durata è uguale a quello della procedura e il relativo ambito è l'intera procedura.  
  
## <a name="calling-syntax"></a>Sintassi di chiamata  
 Si richiama un `Sub` procedure in modo esplicito tramite un'istruzione di chiamata autonoma. È possibile effettuare la chiamata utilizzando il nome in un'espressione. È necessario fornire valori per tutti gli argomenti che non sono facoltativi e, è necessario racchiudere l'elenco di argomenti tra parentesi. Se non vengono forniti argomenti, è possibile omettere le parentesi. L'utilizzo del `Call` (parola chiave) è facoltativo ma non consigliato.  
  
 La sintassi per una chiamata a un `Sub` procedura è la seguente:  
  
 `[Call]`  *subname* `[(` *argumentlist*`)]`  
  
 È possibile chiamare un `Sub` metodo dall'esterno della classe che lo definisce. In primo luogo, è necessario utilizzare il `New` (parola chiave) per creare un'istanza della classe o chiamare un metodo che restituisce un'istanza della classe. Per ulteriori informazioni, vedere [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md). Quindi, è possibile utilizzare la sintassi seguente per chiamare il `Sub` metodo sull'oggetto dell'istanza:  
  
 *Oggetto*. *NomeMetodo*`[(`*argumentlist*`)]`  
  
### <a name="illustration-of-declaration-and-call"></a>Illustrazione di dichiarazione e chiamata  
 Le operazioni seguenti `Sub` procedure indica a quale attività l'applicazione sta per eseguire l'operatore di computer e visualizza un timestamp. Anziché ripetere questo codice all'inizio di ogni attività, l'applicazione chiama semplicemente `tellOperator` da diverse posizioni. Ogni chiamata passa una stringa di `task` argomento che identifica l'attività in corso l'avvio.  
  
 [!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 Nell'esempio seguente viene illustrata una tipica chiamata a `tellOperator`.  
  
 [!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Routine Function](./function-procedures.md)  
 [Routine Property](./property-procedures.md)  
 [Routine di operatore](./operator-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Procedura: Chiamare una routine che non restituisce un valore](./how-to-call-a-procedure-that-does-not-return-a-value.md)  
 [Procedura: chiamare un gestore eventi in Visual Basic](./how-to-call-an-event-handler.md)
