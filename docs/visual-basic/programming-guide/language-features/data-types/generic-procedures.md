---
title: Routine generiche
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
ms.openlocfilehash: 16a629e07cf711778b3d8d1863958ec7a6300649
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350077"
---
# <a name="generic-procedures-in-visual-basic"></a>Generic Procedures in Visual Basic
Una *routine generica*, detta anche *metodo generico*, è una procedura definita con almeno un parametro di tipo. Ciò consente al codice chiamante di adattare i tipi di dati ai relativi requisiti ogni volta che viene chiamata la procedura.  
  
 Una routine non è generica semplicemente in virtù di essere definita all'interno di una classe generica o di una struttura generica. Per essere generico, la routine deve assumere almeno un parametro di tipo, oltre ai parametri normali che potrebbero essere necessari. Una classe o una struttura generica può contenere routine non generiche e una classe, una struttura o un modulo non generico può contenere routine generiche.  
  
 Una routine generica può usare i parametri di tipo nell'elenco di parametri normali, nel tipo restituito, se presente, e nel codice della procedura.  
  
## <a name="type-inference"></a>Inferenza di tipi  
 È possibile chiamare una routine generica senza fornire alcun argomento di tipo. Se viene chiamato in questo modo, il compilatore tenta di determinare i tipi di dati appropriati da passare agli argomenti di tipo della stored procedure. Questa operazione viene definita *inferenza del tipo*. Nel codice seguente viene illustrata una chiamata in cui il compilatore deduce che deve passare il tipo `String` al parametro di tipo `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 Se il compilatore non è in grado di dedurre gli argomenti di tipo dal contesto della chiamata, viene segnalato un errore. Una delle possibili cause di questo errore è la mancata corrispondenza della classificazione della matrice. Si supponga, ad esempio, di definire un parametro normale come matrice di un parametro di tipo. Se si chiama la routine generica che fornisce una matrice di un rango diverso (numero di dimensioni), la mancata corrispondenza causa l'inferenza del tipo. Nel codice seguente viene illustrata una chiamata in cui una matrice bidimensionale viene passata a una routine che prevede una matrice unidimensionale.  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 È possibile richiamare l'inferenza del tipo solo omettendo tutti gli argomenti di tipo. Se si fornisce un solo argomento di tipo, è necessario fornirli tutti.  
  
 L'inferenza del tipo è supportata solo per le routine generiche. Non è possibile richiamare l'inferenza del tipo su classi, strutture, interfacce o delegati generici.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene definita una routine di `Function` generica per trovare un particolare elemento in una matrice. Definisce un parametro di tipo e lo usa per costruire i due parametri nell'elenco di parametri.  
  
### <a name="code"></a>Codice  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a>Comments  
 Nell'esempio precedente è necessario avere la possibilità di confrontare `searchValue` per ogni elemento di `searchArray`. Per garantire questa capacità, vincola il parametro di tipo `T` per implementare l'interfaccia <xref:System.IComparable%601>. Il codice usa il metodo <xref:System.IComparable%601.CompareTo%2A> anziché l'operatore `=`, perché non esiste alcuna garanzia che un argomento di tipo fornito per `T` supporti l'operatore `=`.  
  
 È possibile testare la procedura di `findElement` con il codice seguente.  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 Le chiamate precedenti a `MsgBox` visualizzano rispettivamente "0", "1" e "-1".  
  
## <a name="see-also"></a>Vedere anche

- [Tipi generici in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Procedura: Usare una classe generica](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Routine](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Parametri e argomenti delle routine](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Elenco dei tipi](../../../../visual-basic/language-reference/statements/type-list.md)
- [Elenco dei parametri](../../../../visual-basic/language-reference/statements/parameter-list.md)
