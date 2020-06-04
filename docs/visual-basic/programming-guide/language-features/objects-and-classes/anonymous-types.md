---
title: Tipi anonimi
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousType
helpviewer_keywords:
- anonymous types [Visual Basic], about anonymous types
- anonymous types [Visual Basic]
- types [Visual Basic], anonymous
ms.assetid: 7b87532c-4b3e-4398-8503-6ea9d67574a4
ms.openlocfilehash: bbe84ce8a62705027c00bc26db74a3c21fa34fd9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411799"
---
# <a name="anonymous-types-visual-basic"></a>Tipi anonimi (Visual Basic)
Visual Basic supporta i tipi anonimi, che consentono di creare oggetti senza scrivere una definizione di classe per il tipo di dati. La classe viene generata direttamente dal compilatore. La classe non ha un nome utilizzabile, eredita direttamente da <xref:System.Object> e contiene le proprietà specificate nella dichiarazione dell'oggetto. Poiché il nome del tipo di dati non è specificato, viene definito *tipo anonimo*.  
  
 Nell'esempio seguente viene dichiarata e creata una variabile `product` come istanza di un tipo anonimo con due proprietà, `Name` e `Price` .  
  
 [!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]  
  
 In un' *espressione di query* vengono utilizzati tipi anonimi per combinare colonne di dati selezionati da una query. Non è possibile definire il tipo di risultato in anticipo, perché non è possibile prevedere le colonne che una determinata query potrebbe selezionare. I tipi anonimi consentono di scrivere una query che seleziona un numero qualsiasi di colonne, in qualsiasi ordine. Il compilatore crea un tipo di dati che corrisponde alle proprietà specificate e all'ordine specificato.  
  
 Negli esempi seguenti è riportato `products` un elenco di oggetti Product, ognuno dei quali dispone di molte proprietà. `namePriceQuery`La variabile contiene la definizione di una query che, quando eseguita, restituisce una raccolta di istanze di un tipo anonimo che dispone di due proprietà, `Name` e `Price` .  
  
 [!code-vb[VbVbalrAnonymousTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#2)]  
  
 `nameQuantityQuery`La variabile contiene la definizione di una query che, quando eseguita, restituisce una raccolta di istanze di un tipo anonimo che dispone di due proprietà, `Name` e `OnHand` .  
  
 [!code-vb[VbVbalrAnonymousTypes#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#3)]  
  
 Per altre informazioni sul codice creato dal compilatore per un tipo anonimo, vedere Definizione di [tipo anonimo](anonymous-type-definition.md).  
  
> [!CAUTION]
> Il nome del tipo anonimo è generato dal compilatore e può variare dalla compilazione alla compilazione. Il codice non deve usare o basarsi sul nome di un tipo anonimo perché il nome potrebbe cambiare quando un progetto viene ricompilato.  
  
## <a name="declaring-an-anonymous-type"></a>Dichiarazione di un tipo anonimo  
 La dichiarazione di un'istanza di un tipo anonimo utilizza un elenco di inizializzatori per specificare le proprietà del tipo. È possibile specificare solo le proprietà quando si dichiara un tipo anonimo, non altri elementi della classe, ad esempio metodi o eventi. Nell'esempio seguente `product1` è un'istanza di un tipo anonimo con due proprietà: `Name` e `Price` .  
  
 [!code-vb[VbVbalrAnonymousTypes#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#4)]  
  
 Se si definiscono le proprietà come proprietà chiave, è possibile utilizzarle per confrontare due istanze di tipo anonimo per verificarne l'uguaglianza. Tuttavia, non è possibile modificare i valori delle proprietà chiave. Per ulteriori informazioni, vedere la sezione proprietà chiave più avanti in questo argomento.  
  
 Si noti che la dichiarazione di un'istanza di un tipo anonimo equivale a dichiarare un'istanza di un tipo denominato usando un inizializzatore di oggetto:  
  
 [!code-vb[VbVbalrAnonymousTypes#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#5)]  
  
 Per altre informazioni su altri modi per specificare le proprietà di tipo anonimo, vedere [procedura: dedurre i nomi e i tipi delle proprietà nelle dichiarazioni di tipo anonimo](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà chiave sono diverse dalle proprietà non chiave in diversi modi fondamentali:  
  
- Per determinare se due istanze sono uguali, vengono confrontati solo i valori delle proprietà chiave.  
  
- I valori delle proprietà chiave sono di sola lettura e non possono essere modificati.  
  
- Solo i valori delle proprietà chiave sono inclusi nell'algoritmo del codice hash generato dal compilatore per un tipo anonimo.  
  
### <a name="equality"></a>Uguaglianza  
 Le istanze di tipi anonimi possono essere uguali solo se sono istanze dello stesso tipo anonimo. Il compilatore considera due istanze come istanze dello stesso tipo se soddisfano le condizioni seguenti:  
  
- Sono dichiarati nello stesso assembly.  
  
- Le proprietà hanno gli stessi nomi, gli stessi tipi derivati e vengono dichiarati nello stesso ordine. I confronti tra nomi non fanno distinzione tra maiuscole e minuscole.  
  
- Le stesse proprietà in ogni oggetto sono contrassegnate come proprietà chiave.  
  
- Almeno una proprietà in ogni dichiarazione è una proprietà chiave.  
  
 Un'istanza di tipi anonimi privi di proprietà chiave è uguale solo a se stessa.  
  
 [!code-vb[VbVbalrAnonymousTypes#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#6)]  
  
 Due istanze dello stesso tipo anonimo sono uguali se i valori delle relative proprietà chiave sono uguali. Negli esempi seguenti viene illustrato come verificare l'uguaglianza.  
  
 [!code-vb[VbVbalrAnonymousTypes#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#7)]  
  
### <a name="read-only-values"></a>Valori di sola lettura  
 Non è possibile modificare i valori delle proprietà chiave. Nell' `prod8` esempio precedente, ad esempio, i `Name` `Price` campi e sono `read-only` , ma `OnHand` possono essere modificati.  
  
 [!code-vb[VbVbalrAnonymousTypes#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#8)]  
  
## <a name="anonymous-types-from-query-expressions"></a>Tipi anonimi dalle espressioni di query  
 Le espressioni di query non richiedono sempre la creazione di tipi anonimi. Quando possibile, usano un tipo esistente per conservare i dati della colonna. Questo errore si verifica quando la query restituisce interi record dall'origine dati oppure solo un campo di ogni record. Negli esempi di codice seguenti, `customers` è una raccolta di oggetti di una `Customer` classe. La classe dispone di molte proprietà ed è possibile includerne una o più nel risultato della query, in qualsiasi ordine. Nei primi due esempi, non sono richiesti tipi anonimi perché le query selezionano elementi di tipi denominati:  
  
- `custs1`contiene una raccolta di stringhe, perché `cust.Name` è una stringa.  
  
     [!code-vb[VbVbalrAnonymousTypes#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#30)]  
  
- `custs2`contiene una raccolta di `Customer` oggetti, perché ogni elemento di `customers` è un `Customer` oggetto e l'intero elemento viene selezionato dalla query.  
  
     [!code-vb[VbVbalrAnonymousTypes#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#31)]  
  
 Tuttavia, i tipi denominati appropriati non sono sempre disponibili. Potrebbe essere necessario selezionare i nomi dei clienti e gli indirizzi per uno scopo, i numeri di ID e le località di un altro, nonché i nomi dei clienti, gli indirizzi e le cronologie degli ordini per un terzo. I tipi anonimi consentono di selezionare qualsiasi combinazione di proprietà, in qualsiasi ordine, senza prima dichiarare un nuovo tipo denominato per conservare il risultato. Il compilatore crea invece un tipo anonimo per ogni compilazione di proprietà. La query seguente consente di selezionare solo il nome e il numero ID del cliente da ogni `Customer` oggetto in `customers` . Il compilatore crea pertanto un tipo anonimo che contiene solo le due proprietà.  
  
 [!code-vb[VbVbalrAnonymousTYpes#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#32)]  
  
 Sia i nomi che i tipi di dati delle proprietà nel tipo anonimo vengono ricavati dagli argomenti in `Select` , `cust.Name` e `cust.ID` . Le proprietà in un tipo anonimo creato da una query sono sempre proprietà chiave. Quando `custs3` viene eseguito nel ciclo seguente `For Each` , il risultato è una raccolta di istanze di un tipo anonimo con due proprietà chiave, `Name` e `ID` .  
  
 [!code-vb[VbVbalrAnonymousTypes#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#33)]  
  
 Gli elementi nella raccolta rappresentata da `custs3` sono fortemente tipizzati ed è possibile utilizzare IntelliSense per spostarsi tra le proprietà disponibili e per verificarne i tipi.  
  
 Per ulteriori informazioni, vedere [Introduzione a LINQ in Visual Basic](../linq/introduction-to-linq.md).  
  
## <a name="deciding-whether-to-use-anonymous-types"></a>Decidere se usare i tipi anonimi  
 Prima di creare un oggetto come istanza di una classe anonima, valutare se questa è l'opzione migliore. Se, ad esempio, si desidera creare un oggetto temporaneo per contenere dati correlati e non è necessario disporre di altri campi e metodi che possono essere contenuti in una classe completa, un tipo anonimo è una soluzione efficace. I tipi anonimi sono utili anche se si desidera una selezione diversa delle proprietà per ogni dichiarazione o se si desidera modificare l'ordine delle proprietà. Tuttavia, se il progetto include diversi oggetti con le stesse proprietà, in un ordine fisso, è possibile dichiararli più facilmente usando un tipo denominato con un costruttore di classe. Con un costruttore appropriato, ad esempio, è più semplice dichiarare più istanze di una `Product` classe piuttosto che dichiarare più istanze di un tipo anonimo.  
  
 [!code-vb[VbVbalrAnonymousTypes#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#9)]  
  
 Un altro vantaggio dei tipi denominati è che il compilatore può intercettare un errore di digitazione accidentale di un nome di proprietà. Negli esempi precedenti,, `firstProd2` `secondProd2` e `thirdProd2` sono destinati a essere istanze dello stesso tipo anonimo. Tuttavia, se si desidera dichiarare accidentalmente `thirdProd2` in uno dei modi seguenti, il tipo sarà diverso da quello di `firstProd2` e `secondProd2` .  
  
 [!code-vb[VbVbalrAnonymousTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#10)]  
  
 Ancora più importante, esistono limitazioni sull'uso di tipi anonimi che non si applicano a istanze di tipi denominati. `firstProd2`, `secondProd2` e `thirdProd2` sono istanze dello stesso tipo anonimo. Tuttavia, il nome per il tipo anonimo condiviso non è disponibile e non può essere visualizzato nel punto in cui è previsto il nome di un tipo nel codice. Ad esempio, un tipo anonimo non può essere usato per definire una firma del metodo, per dichiarare un'altra variabile o campo o in qualsiasi dichiarazione di tipo. Di conseguenza, i tipi anonimi non sono appropriati quando è necessario condividere informazioni tra i metodi.  
  
## <a name="an-anonymous-type-definition"></a>Definizione di tipo anonimo  
 In risposta alla dichiarazione di un'istanza di un tipo anonimo, il compilatore crea una nuova definizione di classe che contiene le proprietà specificate.  
  
 Se il tipo anonimo contiene almeno una proprietà chiave, la definizione esegue l'override di tre membri ereditati da <xref:System.Object> : <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> e <xref:System.Object.ToString%2A> . Il codice prodotto per verificare l'uguaglianza e determinare il valore del codice hash considera solo le proprietà chiave. Se il tipo anonimo non contiene proprietà chiave, <xref:System.Object.ToString%2A> viene eseguito l'override di. Le proprietà denominate in modo esplicito di un tipo anonimo non possono essere in conflitto con questi metodi generati. Ovvero, non è possibile utilizzare `.Equals` , `.GetHashCode` o `.ToString` per assegnare un nome a una proprietà.  
  
 Anche le definizioni di tipo anonimo che hanno almeno una proprietà chiave implementano l' <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia, dove `T` è il tipo del tipo anonimo.  
  
 Per altre informazioni sul codice creato dal compilatore e sulle funzionalità dei metodi sottoposti a override, vedere [definizione di tipo anonimo](anonymous-type-definition.md).  
  
## <a name="see-also"></a>Vedere anche

- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](object-initializers-named-and-anonymous-types.md)
- [Inferenza del tipo di variabile locale](../variables/local-type-inference.md)
- [Introduzione a LINQ in Visual Basic](../linq/introduction-to-linq.md)
- [Procedura: dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Definizione di tipo anonimo](anonymous-type-definition.md)
- [Codice](../../../language-reference/modifiers/key.md)
