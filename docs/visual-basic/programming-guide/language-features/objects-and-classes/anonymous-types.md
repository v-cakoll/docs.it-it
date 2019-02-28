---
title: Tipi anonimi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: 5ff3b12e85b9ab7fb8341bb8665a057165e78816
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968018"
---
# <a name="anonymous-types-visual-basic"></a>Tipi anonimi (Visual Basic)
Visual Basic supporta i tipi anonimi, che consentono di creare oggetti senza scrivere una definizione di classe per il tipo di dati. La classe viene generata direttamente dal compilatore. La classe non ha alcun nome utilizzabile, eredita direttamente da <xref:System.Object>e contiene le proprietà specificate nella dichiarazione dell'oggetto. Poiché il nome del tipo di dati non è specificato, viene considerato un *tipo anonimo*.  
  
 Nell'esempio seguente viene dichiarata e crea variabile `product` come un'istanza di un tipo anonimo che ha due proprietà, `Name` e `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 Oggetto *espressione di query* Usa i tipi anonimi per combinare le colonne di dati selezionate da una query. È possibile definire il tipo del risultato in anticipo, poiché non è possibile prevedere le colonne che potrebbe selezionare una determinata query. I tipi anonimi consentono di scrivere una query che seleziona un numero qualsiasi di colonne, in qualsiasi ordine. Il compilatore crea un tipo di dati che corrisponde alla proprietà specificate e l'ordine specificato.  
  
 Negli esempi seguenti, `products` è un elenco di oggetti product, ognuno dei quali ha diverse proprietà. Variabile `namePriceQuery` contiene la definizione di una query che, quando eseguita, restituisce una raccolta di istanze di un tipo anonimo con due proprietà, `Name` e `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#2)]  
  
 Variabile `nameQuantityQuery` contiene la definizione di una query che, quando eseguita, restituisce una raccolta di istanze di un tipo anonimo con due proprietà, `Name` e `OnHand`.  
  
 [!code-vb[VbVbalrAnonymousTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#3)]  
  
 Per altre informazioni sul codice creato dal compilatore per un tipo anonimo, vedere [definizione di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
> [!CAUTION]
>  Il nome del tipo anonimo è generato dal compilatore e può variare da compilazione a compilazione. Il codice deve usare o si basa sul nome di un tipo anonimo perché il nome potrebbe cambiare quando viene ricompilato un progetto.  
  
## <a name="declaring-an-anonymous-type"></a>La dichiarazione di un tipo anonimo  
 La dichiarazione di un'istanza di un tipo anonimo Usa un elenco di inizializzatori per specificare le proprietà del tipo. È possibile specificare solo proprietà quando si dichiara un tipo anonimo, non altri elementi della classe, ad esempio metodi o eventi. Nell'esempio riportato di seguito `product1` è un'istanza di un tipo anonimo che ha due proprietà: `Name` e `Price`.  
  
 [!code-vb[VbVbalrAnonymousTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#4)]  
  
 Se si definiscono le proprietà come proprietà chiave, è possibile usare per confrontare due istanze di tipo anonimo per verificarne l'uguaglianza. Tuttavia, i valori delle proprietà chiave non possono essere modificati. Vedere la sezione delle proprietà di chiave più avanti in questo argomento per altre informazioni.  
  
 Si noti che la dichiarazione di un'istanza di un tipo anonimo è come la dichiarazione di un'istanza di un tipo denominato con un inizializzatore di oggetto:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#5)]  
  
 Per altre informazioni su altri modi per specificare le proprietà di tipo anonimo, vedere [come: In grado di dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà di chiave sono diversi dalle proprietà non chiave in diversi modi fondamentali:  
  
-   Solo i valori delle proprietà chiave vengono confrontati per determinare se due istanze sono uguali.  
  
-   I valori delle proprietà chiave sono di sola lettura e non possono essere modificati.  
  
-   Solo i valori delle proprietà di chiave sono inclusi nell'algoritmo di codice hash generato dal compilatore per un tipo anonimo.  
  
### <a name="equality"></a>Uguaglianza  
 Istanze di tipi anonimi possono essere uguali solo se sono istanze dello stesso tipo anonimo. Il compilatore considera due istanze come istanze dello stesso tipo se soddisfano le condizioni seguenti:  
  
-   Vengono dichiarati nello stesso assembly.  
  
-   Le relative proprietà hanno lo stesso nome, gli stessi tipi derivati e vengono dichiarate nello stesso ordine. I confronti tra nomi non sono tra maiuscole e minuscole.  
  
-   Le stesse proprietà in ogni sono contrassegnate come proprietà chiave.  
  
-   Almeno una proprietà in ogni dichiarazione è una proprietà chiave.  
  
 Un'istanza di tipi anonimi che non ha proprietà chiave è uguale solo a se stesso.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#6)]  
  
 Due istanze dello stesso tipo anonimo sono uguali se i valori delle relative proprietà chiave sono uguali. Gli esempi seguenti illustrano come viene verificata l'uguaglianza.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#7)]  
  
### <a name="read-only-values"></a>Valori di sola lettura  
 I valori delle proprietà chiave non possono essere modificati. Ad esempio, nella `prod8` nell'esempio precedente, il `Name` e `Price` campi sono `read-only`, ma `OnHand` può essere modificato.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/anonymous-types_8.vb)]  
  
## <a name="anonymous-types-from-query-expressions"></a>Tipi anonimi da espressioni di Query  
 Le espressioni di query non richiedono sempre la creazione di tipi anonimi. Quando possibile, usano un tipo esistente per contenere i dati della colonna. Ciò si verifica quando la query restituisce l'intero record dall'origine dei dati, o un solo campo di ogni record. Negli esempi di codice seguente, `customers` è una raccolta di oggetti di un `Customer` classe. La classe dispone di molte proprietà e si può includere uno o più di esse nel risultato della query, in qualsiasi ordine. Nei primi due esempi, non i tipi anonimi sono necessari perché la query Seleziona gli elementi di tipi denominati:  
  
-   `custs1` contiene una raccolta di stringhe, in quanto `cust.Name` è una stringa.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#30)]  
  
-   `custs2` contiene una raccolta di `Customer` oggetti, perché ogni elemento della `customers` è un `Customer` oggetto e l'intero elemento è selezionato dalla query.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#31)]  
  
 Tuttavia, i tipi denominati appropriati non sono sempre disponibili. È possibile selezionare i nomi dei clienti e indirizzi per uno degli scopi, i numeri di ID cliente e percorsi per un altro e i nomi dei clienti, gli indirizzi e le cronologie di ordine per un terzo. I tipi anonimi consentono di selezionare qualsiasi combinazione delle proprietà, in qualsiasi ordine, senza prima dichiarare un nuovo tipo denominato per contenere il risultato. Al contrario, il compilatore crea un tipo anonimo per ogni compilazione delle proprietà. La query seguente consente di selezionare solo il nome del cliente e il numero ID da ognuna `Customer` dell'oggetto `customers`. Pertanto, il compilatore crea un tipo anonimo che contiene solo queste due proprietà.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#32)]  
  
 I nomi e i tipi di dati delle proprietà nel tipo anonimo provengono dagli argomenti per `Select`, `cust.Name` e `cust.ID`. Le proprietà in un tipo anonimo che viene creato da una query sono sempre le proprietà di chiave. Quando `custs3` viene eseguita nell'esempio seguente `For Each` ciclo, il risultato è una raccolta di istanze di un tipo anonimo con due proprietà chiave, `Name` e `ID`.  
  
 [!code-vb[VbVbalrAnonymousTypes#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#33)]  
  
 Gli elementi della raccolta rappresentata da `custs3` sono fortemente tipizzate, ed è possibile usare IntelliSense per spostarsi tra le proprietà disponibili e verificare i relativi tipi.  
  
 Per altre informazioni, vedere [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>Decidere se usare i tipi anonimi  
 Prima di creare un oggetto come un'istanza di una classe anonima, valutare se sia l'opzione migliore. Ad esempio, se si desidera creare un oggetto temporaneo per contenere i dati correlati e non è necessario per gli altri campi e metodi che può contenere una classe completa, un tipo anonimo è un'ottima soluzione. I tipi anonimi sono anche utili se si vuole un'opzione diversa delle proprietà per ogni dichiarazione, o se si desidera modificare l'ordine delle proprietà. Tuttavia, se il progetto include molti oggetti che hanno le stesse proprietà, in un ordine fisso, è possibile dichiararle in più facilmente utilizzando un tipo denominato con un costruttore di classe. Ad esempio, con un costruttore appropriato e risulta più semplice dichiarare più istanze di un `Product` classe anziché dichiarare più istanze di un tipo anonimo.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#9)]  
  
 Un altro vantaggio di tipi denominati è che il compilatore può intercettare un accidentale errata digitazione del nome di una proprietà. Negli esempi precedenti `firstProd2`, `secondProd2`, e `thirdProd2` dovranno essere istanze dello stesso tipo anonimo. Tuttavia, se si dovesse inavvertitamente dichiarare `thirdProd2` in uno dei modi seguenti, è diverso da quello del relativo tipo `firstProd2` e `secondProd2`.  
  
 [!code-vb[VbVbalrAnonymousTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#10)]  
  
 Ancora più importante, esistono limitazioni sull'utilizzo di tipi anonimi che non si applicano alle istanze di tipi denominati. `firstProd2`, `secondProd2`, e `thirdProd2` sono istanze dello stesso tipo anonimo. Tuttavia, il nome per il tipo anonimo condiviso non è disponibile e non può essere specificata in cui è previsto un nome di tipo nel codice. Ad esempio, un tipo anonimo non è utilizzabile per definire una firma del metodo, per dichiarare un'altra variabile o un campo o in qualsiasi dichiarazione di tipo. Di conseguenza, i tipi anonimi non sono appropriati quando si desidera condividere informazioni tra i metodi.  
  
## <a name="an-anonymous-type-definition"></a>Una definizione di tipo anonimo  
 In risposta alla dichiarazione di un'istanza di un tipo anonimo, il compilatore crea una nuova definizione di classe che contiene le proprietà specificate.  
  
 Se il tipo anonimo contiene almeno una proprietà chiave, la definizione esegue l'override di tre membri ereditati da <xref:System.Object>: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, e <xref:System.Object.ToString%2A>. Il codice generato per verificare l'uguaglianza e che determina che il valore del codice hash vengono considerate solo le proprietà della chiave. Se il tipo anonimo non contiene proprietà chiave, solo <xref:System.Object.ToString%2A> viene sottoposto a override. Proprietà denominate in modo esplicito di un tipo anonimo non è in conflitto con questi metodi generati. Vale a dire, non è possibile usare `.Equals`, `.GetHashCode`, o `.ToString` per assegnare un nome di una proprietà.  
  
 Le definizioni di tipo anonimo che hanno almeno una proprietà chiave implementano anche il <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia, in cui `T` è il tipo del tipo anonimo.  
  
 Per altre informazioni sul codice creato dal compilatore e le funzionalità dei metodi sottoposti a override, vedere [definizione di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md).  
  
## <a name="see-also"></a>Vedere anche
- [Inizializzatori di oggetto: Tipi denominati e anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Procedura: Dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Definizione di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
