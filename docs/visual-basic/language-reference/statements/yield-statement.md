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
ms.openlocfilehash: 57b36bb32e1a575a645f7a15045bf0898dd10dfd
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582209"
---
# <a name="yield-statement-visual-basic"></a>Istruzione Yield (Visual Basic)
Invia l'elemento successivo di una raccolta a un'istruzione `For Each...Next`.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a>Parametri  
  
|Termine|Definizione|  
|---|---|  
|`expression`|Obbligatorio. Espressione convertibile in modo implicito nel tipo della funzione iteratore o `Get` funzione di accesso che contiene l'istruzione `Yield`.|  
  
## <a name="remarks"></a>Note  
 L'istruzione `Yield` restituisce un elemento di una raccolta alla volta. L'istruzione `Yield` è inclusa in una funzione iteratore o in una funzione di accesso `Get`, che esegue iterazioni personalizzate su una raccolta.  
  
 Si utilizza una funzione iteratore utilizzando un [per ogni... Istruzione successiva](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o query LINQ. Ogni iterazione del ciclo `For Each` chiama la funzione iteratore. Quando viene raggiunta un'istruzione `Yield` nella funzione iteratore, viene restituito `expression` e viene mantenuta la posizione corrente nel codice. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamata la funzione iteratore.  
  
 Deve esistere una conversione implicita dal tipo di `expression` nell'istruzione `Yield` al tipo restituito dell'iteratore.  
  
 Per terminare l'iterazione, è possibile usare un'istruzione `Exit Function` o `Return`.  
  
 "Yield" non è una parola riservata e ha un significato speciale solo quando viene usato in una funzione `Iterator` o in una funzione di accesso `Get`.  
  
 Per ulteriori informazioni sulle funzioni iteratori e sulle funzioni di accesso `Get`, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Funzioni iteratori e funzioni di accesso get  
 La dichiarazione di una funzione iteratore o di una funzione di accesso `Get` deve soddisfare i requisiti seguenti:  
  
- Deve includere un modificatore [iteratore](../../../visual-basic/language-reference/modifiers/iterator.md) .  
  
- Il tipo restituito deve essere <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.  
  
- Non può avere parametri `ByRef`.  
  
 Una funzione iteratore non può verificarsi in un evento, in un costruttore di istanza, in un costruttore statico o in un distruttore statico.  
  
 Una funzione iteratore può essere una funzione anonima. Per altre informazioni, vedere [Iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Gestione delle eccezioni  
 Un'istruzione `Yield` può trovarsi all'interno di un blocco `Try` di un oggetto [try... Rileva... Istruzione finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Un blocco di `Try` con un'istruzione `Yield` può avere `Catch` blocchi e può avere un blocco `Finally`.  
  
 Un'istruzione `Yield` non può trovarsi all'interno di un blocco di `Catch` o di un blocco di `Finally`.  
  
 Se il corpo del `For Each` (all'esterno della funzione iteratore) genera un'eccezione, un blocco di `Catch` nella funzione iteratore non viene eseguito, ma viene eseguito un blocco `Finally` nella funzione iteratore. Un blocco `Catch` all'interno di una funzione iteratore intercetta solo le eccezioni che si verificano all'interno della funzione iteratore.  
  
## <a name="technical-implementation"></a>Implementazione tecnica  
 Il codice seguente restituisce un `IEnumerable (Of String)` da una funzione iteratore e quindi scorre gli elementi della `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 La chiamata a `MyIteratorFunction` non esegue il corpo della funzione. La chiamata restituisce invece `IEnumerable(Of String)` nella variabile `elements`.  
  
 In un'iterazione del ciclo `For Each`, il metodo <xref:System.Collections.IEnumerator.MoveNext%2A> viene chiamato per `elements`. Questa chiamata esegue il corpo di `MyIteratorFunction` fino a quando non viene raggiunta l'istruzione `Yield` successiva. L'istruzione `Yield` restituisce un'espressione che determina non solo il valore della variabile `element` per l'utilizzo da parte del corpo del ciclo, ma anche la proprietà <xref:System.Collections.Generic.IEnumerator%601.Current%2A> degli elementi, che è un `IEnumerable (Of String)`.  
  
 In ogni iterazione successiva del ciclo `For Each`, l'esecuzione del corpo dell'iteratore continua da dove è stata interrotta, fermandosi ancora quando raggiunge un'istruzione `Yield`. Il ciclo `For Each` viene completato quando viene raggiunta la fine della funzione iteratore o di un'istruzione `Return` o `Exit Function`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è presente un'istruzione `Yield` che si trova all'interno di un oggetto [per... Ciclo successivo](../../../visual-basic/language-reference/statements/for-next-statement.md) . Ogni iterazione del corpo dell'istruzione [for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) in `Main` crea una chiamata al `Power` funzione iteratore. Ogni chiamata alla funzione iteratore procede fino alla prossima esecuzione dell'istruzione `Yield`, che si verifica durante l'iterazione successiva del ciclo `For…Next`.  
  
 Il tipo restituito del metodo iteratore è <xref:System.Collections.Generic.IEnumerable%601>, un tipo di interfaccia iteratore. Quando il metodo iteratore viene chiamato, restituisce un oggetto enumerabile che contiene le potenze di un numero.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una funzione di accesso `Get` che è un iteratore. La dichiarazione di proprietà include un modificatore `Iterator`.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Per altri esempi, vedere [iteratori](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vedere anche

- [Istruzioni](../../../visual-basic/language-reference/statements/index.md)
