---
title: Espressioni - Guida per programmatori C#
ms.date: 05/11/2017
helpviewer_keywords:
- expressions [C#]
- C# language, expressions
ms.assetid: c7d8feb0-0e58-4f94-8bf6-4d070550a832
ms.openlocfilehash: 4bbee8f15c2591e8b172df9a6759449d48697804
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75699093"
---
# <a name="expressions-c-programming-guide"></a>Espressioni (Guida per programmatori C#)

Un'*espressione* è una sequenza di uno o più operandi e zero o più [operatori](../../language-reference/operators/index.md) che può restituire un singolo valore, oggetto, metodo o spazio dei nomi. Le espressioni possono contenere un valore letterale, una chiamata al metodo, un operatore e i relativi operandi oppure un *nome semplice*, ad esempio il nome di una variabile, un membro di un tipo, un parametro di un metodo, uno spazio dei nomi o un tipo.  
  
 Le espressioni possono usare operatori che a loro volta usano altre espressioni come parametri oppure chiamate a metodi i cui parametri sono a loro volta altre chiamate a metodi, quindi le espressioni possono variare da semplici a molto complesse. Di seguito sono riportati due esempi di espressioni:  
  
```csharp  
((x < 10) && ( x > 5)) || ((x > 20) && (x < 25));

System.Convert.ToInt32("35");  
```  
  
## <a name="expression-values"></a>Valori dell'espressione

 Nella maggior parte dei contesti in cui si usano le espressioni, ad esempio in istruzioni o parametri di metodo, l'espressione deve restituire un valore. Se x e y sono numeri interi, l'espressione `x + y` restituisce un valore numerico. L'espressione `new MyClass()` restituisce un riferimento a una nuova istanza di una classe `MyClass`. L'espressione `myClass.ToString()` restituisce una stringa poiché questo è il tipo restituito del metodo. Tuttavia, sebbene il nome di uno spazio dei nomi sia classificato come espressione, non restituisce un valore e quindi non può mai essere il risultato finale di un'espressione. Non è possibile passare il nome di uno spazio dei nomi a un parametro di metodo né usarlo in una nuova espressione o assegnarlo a una variabile. È possibile usarlo solo in un'espressione più ampia come sottoespressione. Lo stesso vale per i tipi (distinti dagli oggetti <xref:System.Type?displayProperty=nameWithType>), i nomi dei gruppi di metodi (distinti dai metodi specifici) e le funzioni di accesso agli eventi [add](../../language-reference/keywords/add.md) e [remove](../../language-reference/keywords/remove.md).  
  
 Ad ogni valore è associato un tipo. Ad esempio, se x e y sono entrambi variabili di tipo `int`, anche il valore dell'espressione `x + y` è di tipo `int`. Se il valore viene assegnato a una variabile di tipo diverso o se x e y sono tipi diversi, vengono applicate le regole di conversione del tipo. Per altre informazioni sul funzionamento di tali conversioni, vedere [Cast e conversioni di tipi](../types/casting-and-type-conversions.md).  
  
## <a name="overflows"></a>Overflow

 Le espressioni numeriche possono causare overflow se il valore è maggiore del valore massimo del tipo del valore. Per ulteriori informazioni, vedere [Checked e Unchecked (Opzione Checked)](../../language-reference/keywords/checked-and-unchecked.md) e la sezione [Conversioni numeriche esplicite](../../language-reference/builtin-types/numeric-conversions.md#explicit-numeric-conversions) dell'articolo [Conversioni numeriche predefinite.](../../language-reference/builtin-types/numeric-conversions.md)
  
## <a name="operator-precedence-and-associativity"></a>Precedenza e associatività degli operatori

 Il modo in cui viene valutata un'espressione è disciplinato dalle regole di associatività e dalla precedenza degli operatori. Per altre informazioni, vedere [Operatori](../../language-reference/operators/index.md).  
  
 La maggior parte delle espressioni, ad eccezione delle espressioni di assegnazione e delle espressioni di chiamata di metodo, devono essere incorporate in un'istruzione. Per altre informazioni, vedere [Istruzioni](./statements.md).  
  
## <a name="literals-and-simple-names"></a>Valori letterali e nomi semplici

 I due tipi più semplici di espressione sono i valori letterali e i nomi semplici. Un valore letterale è un valore costante che non ha un nome. Ad esempio, nel codice seguente sia `5` che `"Hello World"` sono valori letterali:  
  
 [!code-csharp[csProgGuideStatements#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#2)]  
  
 Per altre informazioni sui valori letterali, vedere [Tipi](/dotnet/csharp/language-reference/keywords).  
  
 Nell'esempio precedente, sia `i` che `s` sono nomi semplici che identificano le variabili locali. Quando tali variabili vengono usate in un'espressione, il nome della variabile restituisce il valore attualmente archiviato nel percorso della variabile in memoria. Questa operazione è illustrata nell'esempio seguente:  
  
 [!code-csharp[csProgGuideStatements#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#3)]

## <a name="invocation-expressions"></a>Espressioni di chiamata

 Nell'esempio di codice seguente, la chiamata a `DoWork` è un'espressione di chiamata.  
  
```csharp
DoWork();  
```  
  
 Una chiamata al metodo richiede il nome del metodo, che può essere un nome come nell'esempio precedente o il risultato di un'altra espressione, seguito da parentesi ed eventuali parametri di metodo. Per altre informazioni, vedere [Metodi](../classes-and-structs/methods.md). Una chiamata al delegato usa il nome di un delegato e i parametri di metodo tra parentesi. Per ulteriori informazioni, vedi [Delegati](../delegates/index.md). Le chiamate ai metodi e le chiamate ai delegati restituiscono il valore restituito del metodo, se il metodo restituisce un valore. I metodi che restituiscono void non possono essere usati al posto di un valore in un'espressione.  

## <a name="query-expressions"></a>Espressioni di query

 Per le espressioni di query sono valide le stesse regole applicate in generale per le espressioni. Per altre informazioni, vedere [LINQ](../../linq/index.md).  
  
## <a name="lambda-expressions"></a>Espressioni lambda

 Le espressioni lambda rappresentano "metodi inline" che non hanno nome ma possono avere parametri di input e più istruzioni. Vengono ampiamente usate in LINQ per passare gli argomenti ai metodi. Le espressioni lambda vengono compilate in delegati o alberi delle espressioni a seconda del contesto in cui vengono usate. Per ulteriori informazioni, vedere [Espressioni lambda](lambda-expressions.md).  
  
## <a name="expression-trees"></a>Alberi delle espressioni

Gli alberi delle espressioni consentono di rappresentare le espressioni come strutture dei dati. Vengono ampiamente usati dai provider LINQ per convertire le espressioni di query in un codice che sia significativo in un altro contesto, ad esempio un database SQL. Per altre informazioni, vedere [Alberi delle espressioni (C#)](../concepts/expression-trees/index.md).
  
## <a name="expression-body-definitions"></a>Definizioni del corpo dell'espressione

C# supporta i *membri con corpo di espressione*, che consentono di specificare una definizione concisa del corpo dell'espressione per metodi, costruttori, finalizzatori, proprietà e indicizzatori. Per altre informazioni, vedere [Membri con corpo di espressione](expression-bodied-members.md).

## <a name="remarks"></a>Osservazioni

 Ogni volta che un'espressione identifica una variabile, una proprietà dell'oggetto o l'accesso a un indicizzatore di oggetti, il valore di tale elemento viene usato come valore dell'espressione. Un'espressione può essere inserita ovunque sia richiesto un valore o un oggetto in C#, purché l'espressione alla fine restituisca il tipo richiesto.  

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Espressioni](~/_csharplang/spec/expressions.md) in [Specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Operatori](../../language-reference/operators/index.md)
- [Metodi](../classes-and-structs/methods.md)
- [Delegati](../delegates/index.md)
- [Tipi](../types/index.md)
- [LINQ](../../linq/index.md)
