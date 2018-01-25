---
title: Argomenti denominati e facoltativi (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
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
caps.latest.revision: "43"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e4c57efa4027af5dd6b0476eb65845a39fc0b691
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="named-and-optional-arguments-c-programming-guide"></a>Argomenti denominati e facoltativi (Guida per programmatori C#)
In [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] sono stati introdotti gli argomenti denominati e facoltativi. Gli *argomenti denominati* consentono di specificare un argomento per un particolare parametro associando l'argomento al nome del parametro anziché alla posizione del parametro nell'elenco di parametri. Gli *argomenti facoltativi* consentono di omettere gli argomenti per alcuni parametri. Entrambe le tecniche possono essere usate con i metodi, gli indicizzatori, i costruttori e i delegati.  
  
 Quando si usano gli argomenti denominati e facoltativi, gli argomenti vengono valutati nell'ordine nel quale sono visualizzati nell'elenco di argomenti, non nell'elenco di parametri.  
  
 I parametri denominati e facoltativi, se usati insieme, consentono di specificare gli argomenti solo per alcuni parametri di un elenco di parametri facoltativi. Questa funzionalità semplifica considerevolmente le chiamate alle interfacce COM, ad esempio alle API di automazione di Microsoft Office.  
  
## <a name="named-arguments"></a>Argomenti denominati  
 Gli argomenti denominati evitano di dover ricordare o cercare l'ordine di parametri negli elenchi di parametri dei metodi chiamati. Il parametro per ogni argomento può essere specificato dal nome del parametro. Ad esempio, una funzione che stampa altri dettagli, ad esempio il nome del venditore, il numero dell'ordine e il nome del prodotto, può essere chiamata normalmente inviando gli argomenti relativi alla posizione, nell'ordine definito dalla funzione.
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 Se non si ricorda l'ordine dei parametri, ma se ne conoscono i nomi, è possibile inviare gli argomenti in qualsiasi ordine.  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 Gli argomenti denominati migliorano anche la leggibilità del codice identificando che cosa rappresenta ogni argomento. Nel metodo di esempio riportato di seguito `sellerName` non può essere null o uno spazio vuoto. `sellerName` e `productName` sono di tipi stringa, quindi, anziché inviare argomenti in base alla posizione, è opportuno usare argomenti denominati per evitare ambiguità tra i due e semplificare la lettura del codice.
  
 Se usati con argomenti posizionali, gli argomenti denominati sono validi se 

- non sono seguiti da argomenti posizionali, o

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- _iniziando con C# 7.2_, vengono usati nella posizione corretta. Nell'esempio seguente il parametro `orderNum` è nella posizione corretta, ma non è denominato in modo esplicito.

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 Gli argomenti denominati nell'ordine non corretto sono invece ritenuti non validi se seguiti da argomenti posizionali.

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a>Esempio  
 Il codice seguente implementa gli esempi di questa e altre sezioni.  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]  
  
## <a name="optional-arguments"></a>Argomenti facoltativi  
 La definizione di un metodo, un costruttore, un indicizzatore o un delegato può specificare che i parametri sono obbligatori o facoltativi. Tutte le chiamate devono specificare gli argomenti per tutti i parametri obbligatori, ma possono omettere gli argomenti per i parametri facoltativi.  
  
 Ogni parametro facoltativo ha un valore predefinito incluso nella definizione. Se per il parametro non viene inviato alcun argomento, viene usato il valore predefinito. Il valore predefinito deve essere uno dei tipi di espressioni seguenti:  
  
-   un'espressione costante;  
  
-   un'espressione del form `new ValType()`, dove `ValType` è un tipo di valore, ad esempio [enum](../../../csharp/language-reference/keywords/enum.md) o [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);  
  
-   un'espressione del form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), dove `ValType` è un tipo di valore.  
  
 I parametri facoltativi sono definiti alla fine dell'elenco di parametri, dopo eventuali parametri obbligatori. Se il chiamante specifica un argomento per un parametro di una successione di parametri facoltativi, deve specificare gli argomenti per tutti i parametri facoltativi precedenti. I gap delimitati da virgole nell'elenco di argomenti non sono supportati. Nel codice seguente, ad esempio, il metodo di istanza `ExampleMethod` viene definito con un parametro obbligatorio e due parametri facoltativi.  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]  
  
 La chiamata seguente a `ExampleMethod` genera un errore del compilatore, poiché viene specificato un argomento per il terzo parametro ma non per il secondo.  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 Se, tuttavia, si conosce il nome del terzo parametro, è possibile usare un argomento denominato per eseguire l'attività.  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 IntelliSense usa le parentesi per indicare parametri facoltativi, come mostrato nell'immagine seguente.  
  
 ![Informazioni rapide di IntelliSense per il metodo ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")  
Parametri facoltativi in ExampleMethod  
  
> [!NOTE]
>  È possibile anche dichiarare parametri facoltativi usando la classe .NET <xref:System.Runtime.InteropServices.OptionalAttribute>. I parametri `OptionalAttribute` non richiedono un valore predefinito.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente il costruttore per `ExampleClass` ha un solo parametro facoltativo. Il metodo di istanza `ExampleMethod` ha un solo parametro obbligatorio, `required`, e due parametri facoltativi, `optionalstr` e `optionalint`. Il codice in `Main` illustra i diversi modi in cui è possibile richiamare il costruttore e il metodo.  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]  
  
## <a name="com-interfaces"></a>Interfacce COM  
 Gli argomenti denominati e facoltativi, insieme al supporto per gli oggetti dinamici e ad altri miglioramenti, aumentano considerevolmente l'interoperabilità con le API COM, quali le API di automazione di Office.  
  
 Ad esempio, il metodo [AutoFormat](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.autoformat(v=office.15).aspx) nell'interfaccia [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range(v=office.15).aspx) di Microsoft Office Excel ha sette parametri facoltativi. Questi parametri sono illustrati nell'immagine seguente.  
  
 ![Informazioni rapide di IntelliSense per il metodo AutoFormat.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")  
Parametri di AutoFormat  
  
 In C# 3.0 e versioni precedenti è necessario un argomento per ogni parametro, come illustrato nell'esempio seguente.  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]  
  
 È tuttavia possibile semplificare in modo sostanziale la chiamata a `AutoFormat` mediante argomenti denominati e facoltativi, introdotti in C# 4.0. Gli argomenti denominati e facoltativi consentono di omettere l'argomento per un parametro facoltativo se non si vuole modificare il valore predefinito del parametro. Nella chiamata seguente viene specificato un valore per uno solo dei sette parametri.  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]  
  
 Per altre informazioni ed esempi, vedere [Procedura: Usare argomenti denominati e facoltativi nella programmazione di Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) e [Procedura: Accedere agli oggetti di interoperabilità di Office usando le funzionalità di Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
## <a name="overload-resolution"></a>Overload Resolution  
 L'uso di argomenti denominati e facoltativi influisce sulla risoluzione dell'overload nei modi seguenti:  
  
-   Un metodo, un indicizzatore o un costruttore è un candidato per l'esecuzione se ogni parametro è facoltativo o corrisponde, per nome o per posizione, a un solo argomento nell'istruzione chiamante e tale argomento può essere convertito nel tipo del parametro.  
  
-   Se è disponibile più di un candidato, agli argomenti specificati in modo esplicito vengono applicate le regole di risoluzione dell'overload per le conversioni preferite. Gli argomenti omessi per i parametri facoltativi vengono ignorati.  
  
-   Se due candidati sono giudicati ugualmente validi, la preferenza va a un candidato che non ha parametri facoltativi per i quali sono stati omessi gli argomenti nella chiamata. Si tratta di una conseguenza di una preferenza generale nella risoluzione dell'overload per i candidati che hanno un numero di parametri inferiore.  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Usare argomenti denominati e facoltativi nella programmazione di Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
 [Uso del tipo dinamico](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [Uso dei costruttori](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
 [Uso degli indicizzatori](../../../csharp/programming-guide/indexers/using-indexers.md)
