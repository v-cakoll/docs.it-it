---
title: Istruzione Yield (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: fea91731694f18625e43c5545b353851e72234a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821088"
---
# <a name="yield-statement-visual-basic"></a>Istruzione Yield (Visual Basic)
Invia l'elemento avanti di una raccolta a un `For Each...Next` istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Yield expression  
```  
  
## <a name="parameters"></a>Parametri  
  
|Termine|Definizione|  
|---|---|  
|`expression`|Obbligatorio. Un'espressione che è implicitamente convertibile nel tipo di funzione iteratore o `Get` funzione di accesso che contiene il `Yield` istruzione.|  
  
## <a name="remarks"></a>Note  
 Il `Yield` istruzione restituisce un elemento di una raccolta in una fase. Il `Yield` istruzione è inclusa in una funzione iteratore o `Get` della funzione di accesso, a cui eseguire iterazioni personalizzate in una raccolta.  
  
 Utilizzare una funzione iteratore mediante un [For Each... Istruzione Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o una query LINQ. Ogni iterazione del `For Each` loop chiama la funzione iteratore. Quando un `Yield` viene raggiunta l'istruzione nella funzione iteratore, `expression` viene restituito, e viene mantenuta la posizione corrente nel codice. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.  
  
 Deve esistere una conversione implicita dal tipo della `expression` nella `Yield` istruzione per il tipo restituito dell'iteratore.  
  
 È possibile usare un `Exit Function` o `Return` istruzione per terminare l'iterazione.  
  
 "Yield" non è una parola riservata e ha un significato speciale solo quando viene usata in un' `Iterator` funzione o `Get` della funzione di accesso.  
  
 Per altre informazioni sulle funzioni di iteratore e `Get` funzioni di accesso, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Funzioni di iteratore e funzioni di accesso Get  
 La dichiarazione di una funzione iteratore o `Get` della funzione di accesso deve soddisfare i requisiti seguenti:  
  
-   Deve includere un' [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md) modificatore.  
  
-   Il tipo restituito deve essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.  
  
-   Non può avere qualsiasi `ByRef` parametri.  
  
 Una funzione iteratore non può verificarsi in un evento, costruttore di istanza, costruttore statico o distruttore statico.  
  
 Una funzione iteratore può essere una funzione anonima. Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Gestione delle eccezioni  
 A `Yield` istruzione può essere contenuta in un `Try` blocco di un [Try... Catch... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Oggetto `Try` blocco che ha un `Yield` istruzione può avere `Catch` blocca e può avere un `Finally` blocco.  
  
 Oggetto `Yield` istruzione non può essere all'interno di un `Catch` blocco o un `Finally` blocco.  
  
 Se il `For Each` corpo (all'esterno della funzione iteratore) genera un'eccezione, una `Catch` blocco nella funzione iteratore non viene eseguita, ma un `Finally` try nella funzione iteratore. Oggetto `Catch` blocco all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.  
  
## <a name="technical-implementation"></a>Implementazione tecnica  
 Il codice seguente restituisce un `IEnumerable (Of String)` da una funzione iteratore e quindi scorre gli elementi del `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 La chiamata a `MyIteratorFunction` non esegue il corpo della funzione. La chiamata restituisce invece `IEnumerable(Of String)` nella variabile `elements`.  
  
 In un'iterazione del ciclo `For Each`, il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> viene chiamato per `elements`. Questa chiamata esegue il corpo di `MyIteratorFunction` fino a quando non viene raggiunta l'istruzione `Yield` successiva. Il `Yield` l'istruzione restituisce un'espressione che determina non solo il valore della `element` variabili per l'utilizzo dal corpo del ciclo, ma anche la <xref:System.Collections.Generic.IEnumerator%601.Current%2A> proprietà degli elementi, ovvero un `IEnumerable (Of String)`.  
  
 In ogni iterazione successiva del ciclo `For Each`, l'esecuzione del corpo dell'iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `Yield`. Il `For Each` ciclo viene completato quando la fine della funzione iteratore o un `Return` o `Exit Function` viene raggiunta l'istruzione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente contiene un `Yield` istruzione all'interno di un [per... Avanti](../../../visual-basic/language-reference/statements/for-next-statement.md) ciclo. Ogni iterazione del [per ognuno](../../../visual-basic/language-reference/statements/for-each-next-statement.md) nel corpo dell'istruzione `Main` crea una chiamata al `Power` funzione iteratore. Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.  
  
 Il tipo restituito del metodo iteratore è <xref:System.Collections.Generic.IEnumerable%601>, un tipo interfaccia iteratore. Quando il metodo iteratore viene chiamato, restituisce un oggetto enumerabile che contiene le potenze di un numero.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore. La dichiarazione di proprietà contiene un `Iterator` modificatore.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Per altri esempi, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vedere anche

- [Istruzioni](../../../visual-basic/language-reference/statements/index.md)
