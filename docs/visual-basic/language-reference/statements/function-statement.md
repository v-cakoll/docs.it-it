---
title: Istruzione Function (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: "62"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52e9210f9e715b6055e6ed199ef1aa4b919c6dd6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="function-statement-visual-basic"></a>Istruzione Function (Visual Basic)
Dichiara il nome, parametri e il codice che definiscono un `Function` stored procedure.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Parti  
  
-   `attributelist`  
  
     Facoltativo. Vedere [elenco attributi](attribute-list.md).  
  
-   `accessmodifier`  
  
     Facoltativo. Può essere uno dei seguenti:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Facoltativo. Può essere uno dei seguenti:  
  
    -   [Overload](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Facoltativo. Vedere [condiviso](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Facoltativo. Vedere [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `Async`  
  
     Facoltativo. Vedere [Async](../../../visual-basic/language-reference/modifiers/async.md).  
  
-   `Iterator`  
  
     Facoltativo. Vedere [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Obbligatorio. Nome della routine. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `typeparamlist`  
  
     Facoltativo. Elenco di parametri di tipo per una routine generica. Vedere [digitare elenco](type-list.md).  
  
-   `parameterlist`  
  
     Facoltativo. Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura. Vedere [elenco parametri](parameter-list.md).  
  
-   `returntype`  
  
     Obbligatorio se `Option Strict` è `On`. Tipo di dati del valore restituito da questa procedura.  
  
-   `Implements`  
  
     Facoltativo. Indica che questa procedura consente di implementare una o più `Function` procedure, ciascuno definito in un'interfaccia implementata dalla classe o struttura che contiene questa procedura. Vedere [implementa istruzione](implements-statement.md).  
  
-   `implementslist`  
  
     Necessario se si fornisce `Implements`. Elenco delle routine `Function` implementate.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:  
  
     `interface.definedname`  
  
    |Parte|Descrizione|  
    |---|---|  
    |`interface`|Obbligatorio. Nome di un'interfaccia implementata da questa procedura contenente classe o struttura.|  
    |`definedname`|Obbligatorio. Nome mediante il quale la routine viene definita in `interface`.|  
  
-   `Handles`  
  
     Facoltativo. Indica che questa procedura è possibile gestire uno o più eventi specifici. Vedere [gestisce](handles-clause.md).  
  
-   `eventlist`  
  
     Necessario se si fornisce `Handles`. Elenco di eventi gestiti dalla routine.  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     Ogni `eventspecifier` presenta la sintassi e le parti seguenti:  
  
     `eventvariable.event`  
  
    |Parte|Descrizione|  
    |---|---|  
    |`eventvariable`|Obbligatorio. Variabile oggetto dichiarata con il tipo di dati della classe o struttura che genera l'evento.|  
    |`event`|Obbligatorio. Nome dell'evento che gestisce questa procedura.|  
  
-   `statements`  
  
     Facoltativo. Blocco di istruzioni da eseguire all'interno di questa procedura.  
  
-   `End Function`  
  
     Termina la definizione di questa procedura.  
  
## <a name="remarks"></a>Note  
 Tutto il codice eseguibile deve essere all'interno di una stored procedure. Ogni procedura, a sua volta, viene dichiarata all'interno di una classe, una struttura o un modulo a cui fa riferimento come classe, struttura o un modulo che lo contiene.  
  
 Per restituire un valore al codice chiamante, utilizzare un `Function` procedure; in caso contrario, utilizzare un `Sub` stored procedure.  
  
## <a name="defining-a-function"></a>Definizione di una funzione  
 È possibile definire un `Function` procedura solo a livello di modulo. Pertanto, il contesto della dichiarazione per una funzione deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).  
  
 `Function`procedure per impostazione predefinita l'accesso pubblico. È possibile regolare i livelli di accesso con i modificatori di accesso.  
  
 Oggetto `Function` routine consente di dichiarare il tipo di dati del valore che restituisce la procedura. È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia. Se non si specifica il `returntype` , la procedura restituisce `Object`.  
  
 Se la routine utilizza il `Implements` (parola chiave), classe o struttura deve avere anche un `Implements` istruzione che segue immediatamente il `Class` o `Structure` istruzione. Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`. Tuttavia, il nome con cui si definisce un'interfaccia di `Function` (in `definedname`) non deve necessariamente corrispondere al nome di questa procedura (in `name`).  
  
> [!NOTE]
>  È possibile utilizzare espressioni lambda per definire le espressioni di funzione inline. Per ulteriori informazioni, vedere [espressione di funzione](../../../visual-basic/language-reference/operators/function-expression.md) e [espressioni Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="returning-from-a-function"></a>Restituzione da una funzione  
 Quando il `Function` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione che segue l'istruzione che ha chiamato la routine.  
  
 Per restituire un valore di una funzione, è possibile assegnare il valore per il nome della funzione o includerlo in un `Return` istruzione.  
  
 Il `Return` istruzione contemporaneamente assegna il valore restituito e chiude la funzione, come illustrato nell'esempio seguente.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 Nell'esempio seguente viene assegnato il valore restituito per il nome della funzione `myFunction` e quindi utilizza il `Exit Function` istruzione da restituire.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 Il `Exit Function` e `Return` istruzioni uscire immediatamente da un `Function` stored procedure. Un numero qualsiasi di `Exit Function` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Function` e `Return` istruzioni.  
  
 Se si utilizza `Exit Function` senza assegnare un valore a `name`, la procedura restituisce il valore predefinito per il tipo di dati specificato in `returntype`. Se `returntype` non è specificato, la stored procedure restituisce `Nothing`, ovvero il valore predefinito per `Object`.  
  
## <a name="calling-a-function"></a>Chiamata di una funzione  
 Si chiama un `Function` procedure utilizzando il nome, seguito dall'elenco di argomenti tra parentesi, in un'espressione. È possibile omettere le parentesi solo se non si specificano argomenti. Tuttavia, il codice è più leggibile se si includono sempre le parentesi.  
  
 Si chiama un `Function` routine di funzione, ad esempio nello stesso modo che qualsiasi libreria `Sqrt`, `Cos`, o `ChrW`.  
  
 È inoltre possibile chiamare una funzione mediante il `Call` (parola chiave). In tal caso, il valore restituito viene ignorato. Utilizzare il `Call` (parola chiave) non è consigliata nella maggior parte dei casi. Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).  
  
 Visual Basic vengono a volte riorganizzate espressioni aritmetiche per aumentare l'efficienza interno. Per questo motivo, è consigliabile utilizzare un `Function` procedure in un'espressione aritmetica quando la funzione modifica il valore delle variabili nella stessa espressione.  
  
## <a name="async-functions"></a>Funzioni asincrone  
 Il *Async* funzionalità consente di richiamare funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.  
  
 Se si contrassegna una funzione con il [Async](../../../visual-basic/language-reference/modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore della funzione. Quando il controllo raggiunge un' `Await` espressione il `Async` funzione, il controllo ritorna al chiamante e lo stato di avanzamento nella funzione viene sospeso fino al completamento dell'attività attesa. Quando l'attività viene completata, l'esecuzione può riprendere nella funzione.  
  
> [!NOTE]
>  Un `Async` procedure restituisce al chiamante quando rileva il primo oggetto atteso che non è ancora completo o raggiunge la fine del `Async` procedure, a seconda del valore si verifica per primo.  
  
 Un `Async` funzione può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>. Un esempio di un `Async` funzione che dispone di un tipo restituito di <xref:System.Threading.Tasks.Task%601> di seguito è disponibile.  
  
 Un `Async` funzione non può dichiarare [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parametri.  
  
 A [istruzione Sub](sub-statement.md) può anche essere contrassegnata con il `Async` modificatore. Viene utilizzato principalmente per i gestori eventi, in cui non è possibile restituire un valore. Un `Async``Sub` procedura non può essere atteso e il chiamante di un `Async``Sub` procedura non può intercettare le eccezioni generate dal `Sub` stored procedure.  
  
 Per ulteriori informazioni su `Async` funzioni, vedere [la programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="iterator-functions"></a>Funzioni di iteratore  
 Un *iteratore* funzione esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o matrice. Utilizza una funzione iterator il [Yield](yield-statement.md) istruzione per restituire ogni elemento uno alla volta. Quando un [Yield](yield-statement.md) istruzione viene raggiunto, la posizione corrente nel codice viene memorizzata. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.  
  
 Chiamare un iteratore dal codice client utilizzando un [For Each... Avanti](for-each-next-statement.md) istruzione.  
  
 Può essere il tipo restituito di una funzione iterator <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Function` istruzione per dichiarare il nome, parametri e il codice che formano il corpo di un `Function` stored procedure. Il `ParamArray` modificatore consente alla funzione di accettare un numero variabile di argomenti.  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente richiama la funzione dichiarata nell'esempio precedente.  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, `DelayAsync` è un `Async``Function` che presenta un tipo restituito di <xref:System.Threading.Tasks.Task%601>. `DelayAsync` ha un'istruzione `Return` che restituisce un numero intero. Pertanto la dichiarazione di funzione di `DelayAsync` deve avere un tipo restituito di `Task(Of Integer)`. Poiché il tipo restituito è `Task(Of Integer)`, la valutazione del `Await` espressione `DoSomethingAsync` genera un numero intero. Come illustrato in questa istruzione: `Dim result As Integer = Await delayTask`.  
  
 Il `startButton_Click` procedure è un esempio di un `Async Sub` stored procedure. Poiché `DoSomethingAsync` è un `Async` (funzione), l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustra l'istruzione seguente: `Await DoSomethingAsync()`. Il `startButton_Click``Sub` procedura deve essere definita con la `Async` modificatore perché contiene un `Await` espressione.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Sub](sub-statement.md)  
 [Routine Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Elenco dei parametri](parameter-list.md)  
 [Istruzione Dim](dim-statement.md)  
 [Istruzione Call](call-statement.md)  
 [Of](of-clause.md)  
 [Matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Risoluzione dei problemi relativi alle routine](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Espressione di funzione](../../../visual-basic/language-reference/operators/function-expression.md)
