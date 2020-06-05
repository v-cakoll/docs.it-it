---
title: 'Procedura: dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo'
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: 9ebbbe9d2e6d36f5ab2bc7f7c916d18c9240a06d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404888"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a>Procedura: dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo (Visual Basic)

I tipi anonimi non offrono alcun meccanismo per specificare direttamente i tipi di dati delle proprietà. I tipi di tutte le proprietà vengono dedotti. Nell'esempio seguente, i tipi di `Name` e `Price` vengono dedotti direttamente dai valori usati per inizializzarli.

[!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]

I tipi anonimi possono anche dedurre i nomi e i tipi delle proprietà da altre origini. Le sezioni che seguono forniscono un elenco delle circostanze in cui l'inferenza è possibile e alcuni esempi di situazioni in cui non lo è.

## <a name="successful-inference"></a>Inferenza corretta

#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a>I tipi anonimi possono dedurre i nomi e i tipi delle proprietà dalle origini seguenti:

- Dai nomi di variabili. Il tipo anonimo `anonProduct` avrà due proprietà, `productName` e `productPrice`. I relativi tipi di dati saranno quelli delle variabili originali, `String` e `Double`, rispettivamente.

  [!code-vb[VbVbalrAnonymousTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#11)]

- Dai nomi di proprietà o di campo di altri oggetti. Si consideri ad esempio un oggetto `car` di tipo `CarClass` che include le proprietà `Name` e `ID` . Per creare una nuova istanza di tipo anonimo, `car1`, con le proprietà `Name` e `ID` inizializzate con i valori dell'oggetto `car` , è possibile scrivere quanto segue:

  [!code-vb[VbVbalrAnonymousTypes#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#34)]

  La dichiarazione precedente è equivalente alla riga di codice più lunga che definisce il tipo anonimo `car2`.

  [!code-vb[VbVbalrAnonymousTypes#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#35)]

- Dai nomi di membri XML.

  [!code-vb[VbVbalrAnonymousTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#12)]

  Il tipo risultante per `anon` avrebbe una proprietà, `Book`, di tipo <xref:System.Collections.IEnumerable>(di XElement).

- Da una funzione che non ha parametri, ad esempio `SomeFunction` nell'esempio seguente.

  ```vb
  Dim sc As New SomeClass
  Dim anon1 = New With {Key sc.SomeFunction()}
  ```

  La variabile `anon2` nel codice seguente è un tipo anonimo che ha una proprietà, un carattere denominato `First`. Questo codice visualizzerà una lettera "E", la lettera restituita dalla funzione <xref:System.Linq.Enumerable.First%2A>.

  [!code-vb[VbVbalrAnonymousTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#13)]

## <a name="inference-failures"></a>Inferenze non corrette

#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a>In molte circostanze l'inferenza del nome non avrà successo, come illustrato negli esempi seguenti:

- L'inferenza deriva dalla chiamata di un metodo, di un costruttore o di una proprietà con parametri che richiedono argomenti. La dichiarazione precedente di `anon1` ha esito negativo se `someFunction` ha uno o più argomenti.

  ```vb
  ' Not valid.
  ' Dim anon3 = New With {Key sc.someFunction(someArg)}
  ```

  L'assegnazione a un nuovo nome della proprietà risolve il problema.

  ```vb
  ' Valid.
  Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}
  ```

- L'inferenza deriva da un'espressione complessa.

  ```vb
  Dim aString As String = "Act "
  ' Not valid.
  ' Dim label = New With {Key aString & "IV"}
  ```

  L'errore può essere risolto assegnando il risultato dell'espressione a un nome di proprietà.

  [!code-vb[VbVbalrAnonymousTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#14)]

- L'inferenza per più proprietà produce due o più proprietà che hanno lo stesso nome. Riferendosi di nuovo alle dichiarazioni illustrate negli esempi precedenti, non è possibile elencare `product.Name` e `car1.Name` come proprietà dello stesso tipo anonimo, perché l'identificatore dedotto per ognuno di queste sarebbe `Name`.

  ```vb
  ' Not valid.
  ' Dim anon5 = New With {Key product.Name, Key car1.Name}
  ```

  Il problema può essere risolto assegnando i valori a nomi di proprietà distinti.

  [!code-vb[VbVbalrAnonymousTypes#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#36)]

  Si noti che le differenze di lettere maiuscole o minuscole non differenziano i due nomi.

  ```vb
  Dim price = 0
  ' Not valid, because Price and price are the same name.
  ' Dim anon7 = New With {Key product.Price, Key price}
  ```

- Il tipo e il valore iniziale di una proprietà dipendono da un'altra proprietà non ancora stabilita. Ad esempio, `.IDName = .LastName` non è valido in una dichiarazione di tipo anonimo, a meno che `.LastName` non sia già stato inizializzato.

  ```vb
  ' Not valid.
  ' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}
  ```

  In questo esempio, è possibile risolvere il problema invertendo l'ordine in cui sono dichiarate le proprietà.

  [!code-vb[VbVbalrAnonymousTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#15)]

- Un nome di proprietà del tipo anonimo è uguale al nome di un membro di <xref:System.Object>. Ad esempio, la dichiarazione seguente ha esito negativo perché `Equals` è un metodo di <xref:System.Object>.

  ```vb
  ' Not valid.
  ' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _
  '                       "greater than", Key .Less = "less than"}
  ```

  È possibile risolvere il problema modificando il nome della proprietà:

  [!code-vb[VbVbalrAnonymousTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#16)]

## <a name="see-also"></a>Vedere anche

- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](object-initializers-named-and-anonymous-types.md)
- [Inferenza del tipo di variabile locale](../variables/local-type-inference.md)
- [Tipi anonimi](anonymous-types.md)
- [Codice](../../../language-reference/modifiers/key.md)
