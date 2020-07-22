---
title: Argomenti denominati e facoltativi - Guida per programmatori C#
description: Gli argomenti denominati in C# specificano gli argomenti per nome, non per la posizione. Gli argomenti facoltativi possono essere omessi.
ms.date: 07/20/2015
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
ms.openlocfilehash: 46b9dc23644e68aea2767f2b990fe7f243a4f357
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864982"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a>Argomenti denominati e facoltativi (Guida per programmatori C#)
In C# 4 sono stati introdotti gli argomenti denominati e facoltativi. Gli *argomenti denominati* consentono di specificare un argomento per un particolare parametro associando l'argomento al nome del parametro anziché alla posizione del parametro nell'elenco di parametri. Gli *argomenti facoltativi* consentono di omettere gli argomenti per alcuni parametri. Entrambe le tecniche possono essere usate con i metodi, gli indicizzatori, i costruttori e i delegati.  
  
 Quando si usano gli argomenti denominati e facoltativi, gli argomenti vengono valutati nell'ordine nel quale sono visualizzati nell'elenco di argomenti, non nell'elenco di parametri.  
  
 I parametri denominati e facoltativi, se usati insieme, consentono di specificare gli argomenti solo per alcuni parametri di un elenco di parametri facoltativi. Questa funzionalità semplifica considerevolmente le chiamate alle interfacce COM, ad esempio alle API di automazione di Microsoft Office.  
  
## <a name="named-arguments"></a>Argomenti denominati  
 Gli argomenti denominati evitano di dover ricordare o cercare l'ordine di parametri negli elenchi di parametri dei metodi chiamati. Il parametro per ogni argomento può essere specificato dal nome del parametro. Ad esempio, una funzione che stampa altri dettagli, ad esempio il nome del venditore, il numero dell'ordine e il nome del prodotto, può essere chiamata normalmente inviando gli argomenti relativi alla posizione, nell'ordine definito dalla funzione.
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 Se non si ricorda l'ordine dei parametri, ma se ne conoscono i nomi, è possibile inviare gli argomenti in qualsiasi ordine.  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 Gli argomenti denominati migliorano anche la leggibilità del codice identificando che cosa rappresenta ogni argomento. Nel metodo di esempio riportato di seguito `sellerName` non può essere Null o uno spazio vuoto. `sellerName` e `productName` sono di tipi stringa, quindi, anziché inviare argomenti in base alla posizione, è opportuno usare argomenti denominati per evitare ambiguità tra i due e semplificare la lettura del codice.
  
 Se usati con argomenti posizionali, gli argomenti denominati sono validi se

- non sono seguiti da argomenti posizionali, o

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- _iniziando con C# 7.2_, vengono usati nella posizione corretta. Nell'esempio seguente il parametro `orderNum` è nella posizione corretta, ma non è denominato in modo esplicito.

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 Gli argomenti posizionali che seguono gli argomenti denominati non ordinati non sono validi.

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a>Esempio  
 Il codice seguente implementa gli esempi di questa e altre sezioni.  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]  
  
## <a name="optional-arguments"></a>Argomenti facoltativi  
 La definizione di un metodo, un costruttore, un indicizzatore o un delegato può specificare che i parametri sono obbligatori o facoltativi. Tutte le chiamate devono specificare gli argomenti per tutti i parametri obbligatori, ma possono omettere gli argomenti per i parametri facoltativi.  
  
 Ogni parametro facoltativo ha un valore predefinito incluso nella definizione. Se per il parametro non viene inviato alcun argomento, viene usato il valore predefinito. Il valore predefinito deve essere uno dei tipi di espressioni seguenti:  
  
- un'espressione costante;  
  
- un'espressione del form `new ValType()`, dove `ValType` è un tipo di valore, ad esempio [enum](../../language-reference/builtin-types/enum.md) o [struct](../../language-reference/builtin-types/struct.md);  
  
- un'espressione del form [default(ValType)](../../language-reference/operators/default.md), dove `ValType` è un tipo di valore.  
  
 I parametri facoltativi sono definiti alla fine dell'elenco di parametri, dopo eventuali parametri obbligatori. Se il chiamante specifica un argomento per un parametro di una successione di parametri facoltativi, deve specificare gli argomenti per tutti i parametri facoltativi precedenti. I gap delimitati da virgole nell'elenco di argomenti non sono supportati. Nel codice seguente, ad esempio, il metodo di istanza `ExampleMethod` viene definito con un parametro obbligatorio e due parametri facoltativi.  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]  
  
 La chiamata seguente a `ExampleMethod` genera un errore del compilatore, poiché viene specificato un argomento per il terzo parametro ma non per il secondo.  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 Se, tuttavia, si conosce il nome del terzo parametro, è possibile usare un argomento denominato per eseguire l'attività.  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 IntelliSense usa le parentesi per indicare parametri facoltativi, come illustrato nell'immagine seguente:  
  
 ![Screenshot con le informazioni rapide di IntelliSense per il metodo ExampleMethod.](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)  
  
> [!NOTE]
> È possibile anche dichiarare parametri facoltativi usando la classe .NET <xref:System.Runtime.InteropServices.OptionalAttribute>. I parametri `OptionalAttribute` non richiedono un valore predefinito.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente il costruttore per `ExampleClass` ha un solo parametro facoltativo. Il metodo di istanza `ExampleMethod` ha un solo parametro obbligatorio, `required`, e due parametri facoltativi, `optionalstr` e `optionalint`. Il codice in `Main` illustra i diversi modi in cui è possibile richiamare il costruttore e il metodo.  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]  
  
## <a name="com-interfaces"></a>Interfacce COM  
 Gli argomenti denominati e facoltativi, insieme al supporto per gli oggetti dinamici e ad altri miglioramenti, aumentano considerevolmente l'interoperabilità con le API COM, quali le API di automazione di Office.  
  
 Ad esempio, il metodo <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> nell'interfaccia <xref:Microsoft.Office.Interop.Excel.Range> di Microsoft Office Excel ha sette parametri facoltativi. Questi parametri sono illustrati nell'immagine seguente:  
  
 ![Screenshot con le informazioni rapide di IntelliSense per il metodo AutoFormat.](./media/named-and-optional-arguments/autoformat-method-parameters.png)  
  
 In C# 3.0 e versioni precedenti è necessario un argomento per ogni parametro, come illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]  
  
 È tuttavia possibile semplificare in modo sostanziale la chiamata a `AutoFormat` mediante argomenti denominati e facoltativi, introdotti in C# 4.0. Gli argomenti denominati e facoltativi consentono di omettere l'argomento per un parametro facoltativo se non si vuole modificare il valore predefinito del parametro. Nella chiamata seguente viene specificato un valore per uno solo dei sette parametri.  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]  
  
 Per altre informazioni ed esempi, vedere [come usare gli argomenti denominati e facoltativi nella programmazione di Office](./how-to-use-named-and-optional-arguments-in-office-programming.md) e [come accedere agli oggetti di interoperabilità di Office usando le funzionalità di C#](../interop/how-to-access-office-onterop-objects.md).  
  
## <a name="overload-resolution"></a>Overload Resolution  
 L'uso di argomenti denominati e facoltativi influisce sulla risoluzione dell'overload nei modi seguenti:  
  
- Un metodo, un indicizzatore o un costruttore è un candidato per l'esecuzione se ogni parametro è facoltativo o corrisponde, per nome o per posizione, a un solo argomento nell'istruzione chiamante e tale argomento può essere convertito nel tipo del parametro.  
  
- Se è disponibile più di un candidato, agli argomenti specificati in modo esplicito vengono applicate le regole di risoluzione dell'overload per le conversioni preferite. Gli argomenti omessi per i parametri facoltativi vengono ignorati.  
  
- Se due candidati sono giudicati ugualmente validi, la preferenza va a un candidato che non ha parametri facoltativi per i quali sono stati omessi gli argomenti nella chiamata. Si tratta di una conseguenza di una preferenza generale nella risoluzione dell'overload per i candidati che hanno un numero di parametri inferiore.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Come usare argomenti denominati e facoltativi nella programmazione di Office](./how-to-use-named-and-optional-arguments-in-office-programming.md)
- [Utilizzo del tipo dinamico](../types/using-type-dynamic.md)
- [Utilizzo di costruttori](./using-constructors.md)
- [Utilizzo degli indicizzatori](../indexers/using-indexers.md)
