---
title: Istruzione Yield
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: cc89e6f9bc2ccb4fff9a9fe12cd190a6b2d212dc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401368"
---
# <a name="yield-statement-visual-basic"></a>Istruzione Yield (Visual Basic)
Invia l'elemento successivo di una raccolta a un' `For Each...Next` istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a>Parametri  
  
|Termine|Definizione|  
|---|---|  
|`expression`|Obbligatorio. Espressione convertibile in modo implicito nel tipo della funzione iteratore o della funzione di `Get` accesso che contiene l' `Yield` istruzione.|  
  
## <a name="remarks"></a>Commenti  
 L' `Yield` istruzione restituisce un elemento di una raccolta alla volta. L' `Yield` istruzione è inclusa in una funzione o una funzione di accesso iteratore `Get` che esegue iterazioni personalizzate su una raccolta.  
  
 Si utilizza una funzione iteratore utilizzando un [per ogni... Istruzione successiva](for-each-next-statement.md) o query LINQ. Ogni iterazione del `For Each` ciclo chiama la funzione iteratore. Quando viene `Yield` raggiunta un'istruzione nella funzione iteratore, `expression` viene restituito e viene mantenuta la posizione corrente nel codice. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.  
  
 Deve esistere una conversione implicita dal tipo di `expression` nell' `Yield` istruzione al tipo restituito dell'iteratore.  
  
 È possibile utilizzare un' `Exit Function` `Return` istruzione o per terminare l'iterazione.  
  
 "Yield" non è una parola riservata e ha un significato speciale solo quando viene usato in una `Iterator` funzione o una funzione di `Get` accesso.  
  
 Per ulteriori informazioni sulle funzioni e sulle funzioni di accesso iteratori `Get` , vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Funzioni iteratori e funzioni di accesso get  
 La dichiarazione di una funzione o di una funzione di accesso iteratore `Get` deve soddisfare i requisiti seguenti:  
  
- Deve includere un modificatore [iteratore](../modifiers/iterator.md) .  
  
- Il tipo restituito deve essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.  
  
- Non può avere `ByRef` parametri.  
  
 Una funzione iteratore non può verificarsi in un evento, in un costruttore di istanza, in un costruttore statico o in un distruttore statico.  
  
 Una funzione iteratore può essere una funzione anonima. Per ulteriori informazioni, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Gestione delle eccezioni  
 Un' `Yield` istruzione può trovarsi all'interno `Try` di un blocco di un [try... Rileva... Istruzione finally](try-catch-finally-statement.md). Un `Try` blocco con un' `Yield` istruzione può contenere `Catch` blocchi e può avere un `Finally` blocco.  
  
 Un' `Yield` istruzione non può trovarsi all'interno di un `Catch` blocco o di un `Finally` blocco.  
  
 Se il `For Each` corpo (all'esterno della funzione iteratore) genera un'eccezione, un `Catch` blocco nella funzione iteratore non viene eseguito, ma `Finally` viene eseguito un blocco nella funzione iteratore. Un `Catch` blocco all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.  
  
## <a name="technical-implementation"></a>Implementazione tecnica  
 Il codice seguente restituisce un oggetto `IEnumerable (Of String)` da una funzione iteratore e quindi scorre gli elementi dell'oggetto `IEnumerable (Of String)` .  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 La chiamata a `MyIteratorFunction` non esegue il corpo della funzione. La chiamata restituisce invece `IEnumerable(Of String)` nella variabile `elements`.  
  
 In un'iterazione del ciclo `For Each`, il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> viene chiamato per `elements`. Questa chiamata esegue il corpo di `MyIteratorFunction` fino a quando non viene raggiunta l'istruzione `Yield` successiva. L' `Yield` istruzione restituisce un'espressione che determina non solo il valore della `element` variabile per l'utilizzo da parte del corpo del ciclo, ma anche la <xref:System.Collections.Generic.IEnumerator%601.Current%2A> proprietà degli elementi, ovvero un oggetto `IEnumerable (Of String)` .  
  
 In ogni iterazione successiva del ciclo `For Each`, l'esecuzione del corpo dell'iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `Yield`. Il `For Each` ciclo viene completato quando viene raggiunta la fine della funzione iteratore o un' `Return` `Exit Function` istruzione o.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è presente un' `Yield` istruzione che si trova all'interno di un oggetto [per... Ciclo successivo](for-next-statement.md) . Ogni iterazione del corpo dell'istruzione [for each](for-each-next-statement.md) in `Main` Crea una chiamata alla `Power` funzione iteratore. Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.  
  
 Il tipo restituito del metodo iteratore è <xref:System.Collections.Generic.IEnumerable%601> , un tipo di interfaccia iteratore. Quando il metodo iteratore viene chiamato, restituisce un oggetto enumerabile che contiene le potenze di un numero.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore. La dichiarazione di proprietà include un `Iterator` modificatore.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Per altri esempi, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vedere anche

- [Istruzioni](index.md)
