---
title: Generic Procedures in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 4aed16ce9eb59da54156a0cd5f1594819788521b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818917"
---
# <a name="generic-procedures-in-visual-basic"></a>Generic Procedures in Visual Basic
Oggetto *routine generica*, definita anche come una *metodo generico*, è una routine definita con almeno un parametro di tipo. In questo modo il codice chiamante personalizzare i tipi di dati ai propri requisiti ogni volta che viene chiamata la routine.  
  
 Una procedura non è generica semplicemente perché definita all'interno di una classe generica o una struttura generica. Per essere generico, la routine deve accettare almeno un parametro di tipo, oltre a eventuali parametri normali che potrebbero essere necessari. Una classe generica o una struttura può contenere procedure non generiche e una classe, struttura, o modulo può contenere routine generiche.  
  
 Una routine generica è possibile usare i parametri di tipo nell'elenco dei parametri normali, il tipo restituito se include il codice di uno e nella relativa procedura.  
  
## <a name="type-inference"></a>Inferenza di tipi  
 È possibile chiamare una routine generica senza fornire alcun argomento di tipo affatto. Se viene chiamata in questo modo, il compilatore prova a determinare i tipi di dati appropriato per passare agli argomenti di tipo della stored procedure. Questa operazione viene definita *inferenza del tipo*. Il codice seguente viene illustrata una chiamata in cui il compilatore deduce che il tipo deve passato `String` al parametro di tipo `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 Se il compilatore non è possibile dedurre gli argomenti tipo dal contesto della chiamata, viene segnalato un errore. Una delle possibili cause di questo errore è una mancata corrispondenza del numero di dimensioni matrice. Ad esempio, si supponga di che definisce un parametro normale come una matrice di un parametro di tipo. Se si chiama la routine generica fornendo una matrice di una dimensione differente (numero di dimensioni), la mancata corrispondenza causa l'inferenza del tipo esito negativo. Il codice seguente viene illustrata una chiamata in una matrice bidimensionale che viene passata a una procedura che prevede una matrice unidimensionale.  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 È possibile richiamare l'inferenza del tipo solo tramite l'omissione di tutti gli argomenti tipo. Se si specifica un argomento di tipo, è necessario fornire tutti.  
  
 L'inferenza del tipo è supportato solo per routine generiche. Non è possibile richiamare l'inferenza del tipo in classi generiche, strutture, interfacce o delegati.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 L'esempio seguente definisce un oggetto generico `Function` procedura per trovare un particolare elemento in una matrice. Definisce un parametro di tipo e lo usa per costruire i due parametri nell'elenco dei parametri.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a>Commenti  
 Nell'esempio precedente richiede la possibilità di confrontare `searchValue` rispetto a ogni elemento di `searchArray`. Per garantire questa operazione, vincola il parametro di tipo `T` per implementare il <xref:System.IComparable%601> interfaccia. Il codice Usa il <xref:System.IComparable%601.CompareTo%2A> invece del metodo di `=` operatore, poiché non c'è garanzia che un argomento tipo fornito per `T` supporta la `=` operatore.  
  
 È possibile testare il `findElement` procedure con il codice seguente.  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 Nelle chiamate precedenti a `MsgBox` visualizzare rispettivamente "0", "1" e "-1".  
  
## <a name="see-also"></a>Vedere anche

- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Procedura: Usare una classe generica](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Routine](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Parametri e argomenti delle routine](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Elenco dei tipi](../../../../visual-basic/language-reference/statements/type-list.md)
- [Elenco dei parametri](../../../../visual-basic/language-reference/statements/parameter-list.md)
