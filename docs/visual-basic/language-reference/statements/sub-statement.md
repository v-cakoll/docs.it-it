---
title: Istruzione Sub (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0a2d0d5ffdca857a3a5ca58cd38b0930f254526f
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2017
---
# <a name="sub-statement-visual-basic"></a>Istruzione Sub (Visual Basic)
Dichiara il nome, parametri e il codice che definiscono un `Sub` stored procedure.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Parti  
  
-   `attributelist`  
  
     Parametro facoltativo. Vedere [elenco attributi](attribute-list.md).  
  
-   `Partial`  
  
     Parametro facoltativo. Indica la definizione di un metodo parziale. Vedere [metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).  
  
-   `accessmodifier`  
  
     Parametro facoltativo. Può essere uno dei seguenti:  
  
    -   [Public](../modifiers/public.md)  
  
    -   [Protected](../modifiers/protected.md)  
  
    -   [Friend](../modifiers/friend.md)  
  
    -   [Private](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `proceduremodifiers`  
  
     Parametro facoltativo. Può essere uno dei seguenti:  
  
    -   [Overload](../modifiers/overloads.md)  
  
    -   [Overrides](../modifiers/overrides.md)  
  
    -   [Overridable](../modifiers/overridable.md)  
  
    -   [NotOverridable](../modifiers/notoverridable.md)  
  
    -   [MustOverride](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Parametro facoltativo. Vedere [condiviso](../modifiers/shared.md).  
  
-   `Shadows`  
  
     Parametro facoltativo. Vedere [Shadows](../modifiers/shadows.md).  
  
-   `Async`  
  
     Parametro facoltativo. Vedere [Async](../modifiers/async.md).  
  
-   `name`  
  
     Obbligatorio. Nome della routine. Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md). Per creare una routine di costruttore per una classe, impostare il nome di un `Sub` procedura per la `New` (parola chiave). Per ulteriori informazioni, vedere [durata degli oggetti: come gli oggetti sono di creare e distruggere](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
-   `typeparamlist`  
  
     Parametro facoltativo. Elenco di parametri di tipo per una routine generica. Vedere [digitare elenco](type-list.md).  
  
-   `parameterlist`  
  
     Parametro facoltativo. Elenco di nomi di variabili locali che rappresentano i parametri di questa procedura. Vedere [elenco parametri](parameter-list.md).  
  
-   `Implements`  
  
     Parametro facoltativo. Indica che questa procedura consente di implementare una o più `Sub` procedure, ciascuno definito in un'interfaccia implementata dalla classe o struttura che contiene questa procedura. Vedere [implementa istruzione](implements-statement.md).  
  
-   `implementslist`  
  
     Necessario se si fornisce `Implements`. Elenco delle routine `Sub` implementate.  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     Ogni `implementedprocedure` presenta la sintassi e le parti seguenti:  
  
     `interface.definedname`  
  
    |Parte|Descrizione|  
    |---|---|  
    |`interface`|Obbligatorio. Nome di un'interfaccia implementata da questa procedura contenente classe o struttura.|  
    |`definedname`|Obbligatorio. Nome mediante il quale la routine viene definita in `interface`.|  
  
-   `Handles`  
  
     Parametro facoltativo. Indica che questa procedura è possibile gestire uno o più eventi specifici. Vedere [gestisce](handles-clause.md).  
  
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
  
     Parametro facoltativo. Blocco di istruzioni da eseguire all'interno di questa procedura.  
  
-   `End Sub`  
  
     Termina la definizione di questa procedura.  
  
## <a name="remarks"></a>Note  
 Tutto il codice eseguibile deve essere all'interno di una stored procedure. Utilizzare un `Sub` procedure quando non si desidera restituire un valore al codice chiamante. Utilizzare un `Function` procedura quando si desidera restituire un valore.  
  
## <a name="defining-a-sub-procedure"></a>Definizione di una routine Sub  
 È possibile definire un `Sub` procedura solo a livello di modulo. Il contesto della dichiarazione per una routine sub, pertanto, deve essere una classe, una struttura, un modulo o un'interfaccia e non può essere un file di origine, uno spazio dei nomi, una routine o un blocco. Per altre informazioni, vedere [Contesti delle dichiarazioni e livelli di accesso predefiniti](declaration-contexts-and-default-access-levels.md).  
  
 `Sub`procedure per impostazione predefinita l'accesso pubblico. È possibile regolare i livelli di accesso tramite i modificatori di accesso.  
  
 Se la routine utilizza il `Implements` (parola chiave), classe o struttura deve avere un `Implements` istruzione che segue immediatamente il `Class` o `Structure` istruzione. Il `Implements` istruzione deve includere ogni interfaccia specificata in `implementslist`. Tuttavia, il nome con cui si definisce un'interfaccia di `Sub` (in `definedname`) non deve corrispondere al nome di questa procedura (in `name`).  
  
## <a name="returning-from-a-sub-procedure"></a>Restituzione da una routine Sub  
 Quando un `Sub` routine restituisce al codice chiamante, l'esecuzione continua con l'istruzione successiva all'istruzione che lo hanno chiamato.  
  
 Nell'esempio seguente viene restituito da un `Sub` stored procedure.  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 Il `Exit Sub` e `Return` istruzioni uscire immediatamente da un `Sub` stored procedure. Un numero qualsiasi di `Exit Sub` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Sub` e `Return` istruzioni.  
  
## <a name="calling-a-sub-procedure"></a>La chiamata a una routine Sub  
 Si chiama un `Sub` procedure utilizzando il nome della stored procedure in un'istruzione e quindi seguendo questo nome con il relativo elenco di argomenti tra parentesi. È possibile omettere le parentesi solo se non si specifica alcun argomento. Tuttavia, il codice è più leggibile se si includono sempre le parentesi.  
  
 Oggetto `Sub` procedure e un `Function` procedura può avere parametri ed eseguire una serie di istruzioni. Tuttavia, un `Function` stored procedure restituisce un valore e un `Sub` non di procedura. Pertanto, è possibile utilizzare un `Sub` procedure in un'espressione.  
  
 È possibile utilizzare il `Call` (parola chiave) quando si chiama un `Sub` routine, ma tale parola chiave non è consigliato per la maggior parte degli utilizzi. Per ulteriori informazioni, vedere [istruzione Call](call-statement.md).  
  
 Visual Basic vengono a volte riorganizzate espressioni aritmetiche per aumentare l'efficienza interno. Per questo motivo, se all'elenco di argomenti include espressioni che chiamano altre procedure, non deve presupporre che le espressioni verranno chiamate in un ordine particolare.  
  
## <a name="async-sub-procedures"></a>Async Sub (routine)  
 Tramite la funzionalità Async, è possibile richiamare funzioni asincrone senza usare callback espliciti o suddividere manualmente il codice in più funzioni o espressioni lambda.  
  
 Se si contrassegna una procedura con il [Async](../modifiers/async.md) modificatore, è possibile utilizzare il [Await](../../../visual-basic/language-reference/operators/await-operator.md) operatore nella procedura. Quando il controllo raggiunge un' `Await` espressione il `Async` procedure, il controllo ritorna al chiamante e lo stato di avanzamento della procedura viene sospeso fino al completamento dell'attività attesa. Quando l'attività viene completata, l'esecuzione può riprendere nella procedura.  
  
> [!NOTE]
>  Un `Async` routine restituisce al chiamante quando viene rilevato un il primo oggetto atteso che non è ancora completo o alla fine del `Async` stored procedure viene raggiunto, qualunque si verifichi prima.  
  
 È inoltre possibile contrassegnare un [istruzione Function](function-statement.md) con il `Async` modificatore. Un `Async` funzione può avere un tipo restituito di <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>. Un esempio più avanti in questo argomento viene illustrato un `Async` funzione che dispone di un tipo restituito di <xref:System.Threading.Tasks.Task%601>.  
  
 `Async``Sub` procedure vengono utilizzate principalmente per i gestori eventi, in cui non è possibile restituire un valore. Un `Async``Sub` procedura non può essere atteso e il chiamante di un `Async``Sub` procedura non può intercettare le eccezioni che il `Sub` genera stored procedure.  
  
 Un `Async` procedura non può dichiarare [ByRef](../modifiers/byref.md) parametri.  
  
 Per ulteriori informazioni su `Async` procedure, vedere [la programmazione asincrona con Async e Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flusso di controllo in programmi asincroni](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), e [tipi restituiti asincroni](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Sub` istruzione per definire il nome, parametri e il codice che formano il corpo di un `Sub` stored procedure.  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, `DelayAsync` è un `Async``Function` che presenta un tipo restituito di <xref:System.Threading.Tasks.Task%601>. `DelayAsync` ha un'istruzione `Return` che restituisce un numero intero. Pertanto, la dichiarazione di funzione di `DelayAsync` deve avere un tipo restituito di `Task(Of Integer)`. Poiché il tipo restituito è `Task(Of Integer)`, la valutazione del `Await` espressione `DoSomethingAsync` genera un numero intero, come illustrato nell'istruzione seguente: `Dim result As Integer = Await delayTask`.  
  
 Il `startButton_Click` procedure è un esempio di un `Async Sub` stored procedure. Poiché `DoSomethingAsync` è un `Async` (funzione), l'attività per la chiamata a `DoSomethingAsync` deve essere attesa, come illustrato nell'istruzione seguente: `Await DoSomethingAsync()`. Il `startButton_Click``Sub` procedura deve essere definita con la `Async` modificatore perché contiene un `Await` espressione.  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Implements](implements-statement.md)  
 [Istruzione Function](function-statement.md)  
 [Elenco dei parametri](parameter-list.md)  
 [Istruzione Dim](dim-statement.md)  
 [Istruzione Call](call-statement.md)  
 [Of](of-clause.md)  
 [Matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [Procedura: Usare una classe generica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Risoluzione dei problemi relativi alle routine](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [Metodi parziali](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
