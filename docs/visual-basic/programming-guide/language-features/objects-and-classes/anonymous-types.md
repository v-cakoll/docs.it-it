---
title: Tipi anonimi (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
caps.latest.revision: "46"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 530e21e1595f9bbc3436280418287413e2a48111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-types-visual-basic"></a>Tipi anonimi (Visual Basic)
Visual Basic supporta i tipi anonimi che consentono di creare oggetti senza scrivere una definizione di classe per il tipo di dati. La classe viene generata direttamente dal compilatore. La classe ha un nome utilizzabile, eredita direttamente da <xref:System.Object>e contiene le proprietà specificate nella dichiarazione dell'oggetto. Poiché il nome del tipo di dati non è specificato, viene considerato un *tipo anonimo*.  
  
 Nell'esempio seguente viene dichiarata e creata variabile `product` come un'istanza di un tipo anonimo che ha due proprietà, `Name` e `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_1.vb)]  
  
 Oggetto *espressione di query* utilizza tipi anonimi per combinare colonne di dati selezionati da una query. È possibile definire il tipo del risultato in anticipo, perché non è possibile prevedere le colonne di che una particolare query è possibile selezionare. Tipi anonimi consentono di scrivere una query che seleziona un numero qualsiasi di colonne, in qualsiasi ordine. Il compilatore crea un tipo di dati che soddisfi le proprietà specificate e l'ordine specificato.  
  
 Negli esempi seguenti, `products` è un elenco di oggetti product, ognuno dei quali dispone di molte proprietà. Variabile `namePriceQuery` contiene la definizione di una query che, quando eseguita, restituisce una raccolta di istanze di un tipo anonimo che ha due proprietà, `Name` e `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_2.vb)]  
  
 Variabile `nameQuantityQuery` contiene la definizione di una query che, quando eseguita, restituisce una raccolta di istanze di un tipo anonimo che ha due proprietà, `Name` e `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_3.vb)]  
  
 Per ulteriori informazioni sul codice creato dal compilatore per un tipo anonimo, vedere [definizione di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
> [!CAUTION]
>  Il nome del tipo anonimo è generato dal compilatore e può variare da compilazione a compilazione. Il codice non deve usare o basarsi sul nome di un tipo anonimo, poiché il nome potrebbe cambiare quando un progetto viene ricompilato.  
  
## <a name="declaring-an-anonymous-type"></a>Dichiarazione di un tipo anonimo  
 La dichiarazione di un'istanza di un tipo anonimo contiene un elenco di inizializzatori per specificare le proprietà del tipo. È possibile specificare solo le proprietà quando si dichiara un tipo anonimo, non altri elementi della classe, ad esempio metodi o eventi. Nell'esempio seguente, `product1` è un'istanza di un tipo anonimo che ha due proprietà: `Name` e `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_4.vb)]  
  
 Se si impostano le proprietà come proprietà chiave, è possibile utilizzare per confrontare due istanze di tipo anonimo per verificarne l'uguaglianza. Tuttavia, i valori delle proprietà chiave non possono essere modificati. Vedere la sezione di proprietà di chiave più avanti in questo argomento per ulteriori informazioni.  
  
 Si noti che la dichiarazione di un'istanza di un tipo anonimo è come dichiarare un'istanza di un tipo denominato con un inizializzatore di oggetto:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_5.vb)]  
  
 Per ulteriori informazioni su altri modi per specificare le proprietà di tipo anonimo, vedere [procedura: dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="key-properties"></a>Proprietà chiave  
 Proprietà chiave differiscono dalle proprietà non chiave nei vari aspetti fondamentali:  
  
-   Solo i valori delle proprietà chiave vengono confrontati per determinare se due istanze sono uguali.  
  
-   I valori delle proprietà chiave sono di sola lettura e non possono essere modificati.  
  
-   Solo i valori delle proprietà chiave sono inclusi nell'algoritmo codice hash generato dal compilatore per un tipo anonimo.  
  
### <a name="equality"></a>Uguaglianza  
 Istanze di tipi anonimi possono essere uguali solo se sono istanze dello stesso tipo anonimo. Il compilatore considera due istanze come istanze dello stesso tipo che soddisfano le condizioni seguenti:  
  
-   Vengono dichiarati nello stesso assembly.  
  
-   Le proprietà hanno lo stesso nome, gli stessi tipi dedotti e vengono dichiarate nello stesso ordine. Confronti tra nomi non è rilevanti.  
  
-   Le stesse proprietà in ogni sono contrassegnate come proprietà chiave.  
  
-   Almeno una proprietà in ogni dichiarazione è una proprietà chiave.  
  
 Un'istanza di tipi anonimi che non ha proprietà chiave è uguale solo a se stesso.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_6.vb)]  
  
 Due istanze dello stesso tipo anonimo sono uguali se i valori delle relative proprietà chiave sono uguali. Nell'esempio seguente viene illustrato come viene verificata l'uguaglianza.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_7.vb)]  
  
### <a name="read-only-values"></a>Valori di sola lettura  
 I valori delle proprietà chiave non possono essere modificati. Ad esempio, in `prod8` nell'esempio precedente, il `Name` e `Price` i campi sono `read-only`, ma `OnHand` può essere modificato.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_8.vb)]  
  
## <a name="anonymous-types-from-query-expressions"></a>Tipi anonimi da espressioni di Query  
 Le espressioni di query non richiedono sempre la creazione di tipi anonimi. Quando possibile, utilizzano un tipo esistente per contenere i dati della colonna. Questo errore si verifica quando la query restituisce record interi dall'origine dei dati, o un solo campo di ogni record. Negli esempi di codice seguente, `customers` è una raccolta di oggetti di un `Customer` classe. La classe dispone di molte proprietà e il risultato della query, in qualsiasi ordine, è possibile includere uno o più di esse. Nei primi due esempi, i tipi anonimi non sono necessari poiché le query selezionano gli elementi di tipi denominati:  
  
-   `custs1`contiene una raccolta di stringhe, poiché `cust.Name` è una stringa.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_9.vb)]  
  
-   `custs2`contiene una raccolta di `Customer` oggetti, perché ogni elemento di `customers` è un `Customer` oggetto e l'intero elemento è selezionato dalla query.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_10.vb)]  
  
 Tuttavia, i tipi denominati appropriati non sono sempre disponibili. È consigliabile selezionare i nomi dei clienti e gli indirizzi per uno scopo, i numeri di ID cliente e percorsi per un altro e i nomi dei clienti, indirizzi e cronologie di ordine per una terza. Tipi anonimi consentono di selezionare qualsiasi combinazione delle proprietà, in qualsiasi ordine, senza prima dichiarazione di un nuovo tipo denominato per contenere il risultato. Al contrario, il compilatore crea un tipo anonimo per ogni compilazione di proprietà. La query seguente consente di selezionare solo il nome del cliente e il numero di ID da ogni `Customer` oggetto `customers`. Pertanto, il compilatore crea un tipo anonimo che contiene solo queste due proprietà.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_11.vb)]  
  
 I nomi e i tipi di dati delle proprietà nel tipo anonimo vengono acquisiti dagli argomenti a `Select`, `cust.Name` e `cust.ID`. Le proprietà in un tipo anonimo che viene creato da una query sono sempre le proprietà chiave. Quando `custs3` viene eseguita nell'esempio seguente `For Each` ciclo, il risultato è una raccolta di istanze di un tipo anonimo con due proprietà chiave, `Name` e `ID`.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_12.vb)]  
  
 Gli elementi nella raccolta rappresentata da `custs3` sono fortemente tipizzati, ed è possibile utilizzare IntelliSense per spostarsi tra le proprietà disponibili e verificare i relativi tipi.  
  
 Per ulteriori informazioni, vedere [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>Decidere se utilizzare i tipi anonimi  
 Prima di creare un oggetto come un'istanza di una classe anonima, valutare se sia l'opzione migliore. Ad esempio, se si desidera creare un oggetto temporaneo per contenere dati correlati e non sono necessari gli altri campi e metodi che può contenere una classe completa, un tipo anonimo è una buona soluzione. Tipi anonimi sono anche utili se si desidera una selezione di proprietà diversa per ogni dichiarazione, o se si desidera modificare l'ordine delle proprietà. Tuttavia, se il progetto include diversi oggetti che hanno le stesse proprietà, in un ordine fisso, è possibile dichiarare le più facilmente utilizzando un tipo denominato con un costruttore di classe. Ad esempio, con un costruttore adeguato, risulta più semplice dichiarare istanze diverse di un `Product` classe anziché dichiarare molte istanze di un tipo anonimo.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_13.vb)]  
  
 Un altro vantaggio dei tipi denominati è che il compilatore può intercettare un male accidentale di un nome di proprietà. Negli esempi precedenti, `firstProd2`, `secondProd2`, e `thirdProd2` devono essere istanze dello stesso tipo anonimo. Tuttavia, se si dovesse involontariamente dichiarare `thirdProd2` in uno dei modi seguenti, sarebbe diverso da quello del relativo tipo `firstProd2` e `secondProd2`.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_14.vb)]  
  
 Ancora più importante, esistono limitazioni relative all'utilizzo di tipi anonimi che non si applicano alle istanze di tipi denominati. `firstProd2`, `secondProd2`, e `thirdProd2` sono istanze dello stesso tipo anonimo. Tuttavia, il nome per il tipo anonimo condiviso non è disponibile e non può trovarsi in cui è previsto un nome di tipo nel codice. Ad esempio, un tipo anonimo non può essere utilizzato per definire una firma del metodo, per dichiarare un'altra variabile o un campo o in qualsiasi dichiarazione di tipo. Di conseguenza, i tipi anonimi non sono appropriati, quando si desidera condividere informazioni tra i metodi.  
  
## <a name="an-anonymous-type-definition"></a>Una definizione di tipo anonimo  
 In risposta alla dichiarazione di un'istanza di un tipo anonimo, il compilatore crea una nuova definizione di classe che contiene le proprietà specificate.  
  
 Se il tipo anonimo contiene almeno una proprietà chiave, la definizione esegue l'override di tre membri ereditati da <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, e <xref:System.Object.ToString%2A>. Il codice prodotto per verificare l'uguaglianza e per determinare che il valore del codice hash considera solo le proprietà chiave. Se il tipo anonimo non contiene proprietà chiave, solo <xref:System.Object.ToString%2A> viene sottoposto a override. Proprietà denominate in modo esplicito di un tipo anonimo non è in conflitto con questi metodi generati. Ovvero, non è possibile utilizzare `.Equals`, `.GetHashCode`, o `.ToString` per assegnare un nome di una proprietà.  
  
 Definizioni di tipo anonimo che hanno almeno una proprietà chiave implementano anche il <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia, in cui `T` è il tipo del tipo anonimo.  
  
 Per ulteriori informazioni sul codice creato dal compilatore e le funzionalità di metodi sottoposti a override, vedere [definizione di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Procedura: Dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Definizione di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)
