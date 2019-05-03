---
title: 'Inizializzatori di oggetti: Tipi denominati e anonimi (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
ms.openlocfilehash: 6602a68555e37bf793ba41076ba8f484b4a0dbc3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760753"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Inizializzatori di oggetti: Tipi denominati e anonimi (Visual Basic)
Gli inizializzatori di oggetto consentono di specificare le proprietà per un oggetto complesso usando un'unica espressione. Possono essere utilizzati per creare istanze di tipi denominati e tipi anonimi.  
  
## <a name="declarations"></a>Dichiarazioni  
 Le dichiarazioni delle istanze di tipi denominati e anonimi possono sembrano quasi identiche, ma i relativi effetti non sono uguali. Ogni categoria dispone di funzionalità e restrizioni di propri. Nell'esempio seguente viene illustrato un modo pratico per dichiarare e inizializzare un'istanza di una classe denominata, `Customer`, usando un elenco di inizializzatori di oggetto. Si noti che dopo la parola chiave viene specificato il nome della classe `New`.  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 Un tipo anonimo non hanno nome utilizzabile. Creazione di un'istanza di un tipo anonimo non può pertanto includere un nome di classe.  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 I requisiti e i risultati delle due dichiarazioni non corrispondono. Per la `namedCust`, una `Customer` classe avente un `Name` proprietà deve esistere già e la dichiarazione crea un'istanza di tale classe. Per la `anonymousCust`, il compilatore definisce una nuova classe che ha una proprietà, una stringa denominata `Name`e crea una nuova istanza della classe.  
  
## <a name="named-types"></a>Tipi denominati  
 Gli inizializzatori di oggetto forniscono un modo semplice per chiamare il costruttore di un tipo e quindi impostare i valori di alcune o tutte le proprietà in una singola istruzione. Il compilatore richiama il costruttore appropriato per l'istruzione: il costruttore predefinito se non vengono visualizzati argomenti o un costruttore con parametri, se uno o più argomenti vengono inviati. Successivamente, le proprietà specificate vengono inizializzate nell'ordine in cui sono presentate nell'elenco di inizializzatori.  
  
 Ogni inizializzazione nell'elenco di inizializzatori è costituito dall'assegnazione di un valore iniziale a un membro della classe. I nomi e tipi di dati dei membri vengono determinati quando la classe è definita. Negli esempi seguenti, il `Customer` classe deve esistere e devono avere membri denominati `Name` e `City` che può accettare i valori di stringa.  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 In alternativa, è possibile ottenere lo stesso risultato utilizzando il codice seguente:  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 Ognuna di queste dichiarazioni è equivalente all'esempio seguente, che consente di creare un `Customer` dell'oggetto usando il costruttore predefinito e specifica i valori iniziali per il `Name` e `City` delle proprietà utilizzando un `With` istruzione.  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 Se il `Customer` classe contiene un costruttore con parametri che è possibile inviare un valore per `Name`, ad esempio, è possibile anche dichiarare e inizializzare un `Customer` oggetto nei modi seguenti:  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 Non è necessario inizializzare tutte le proprietà, come illustrato nel codice seguente.  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 Tuttavia, l'elenco di inizializzazione non può essere vuoto. Le proprietà non inizializzate mantengono i valori predefiniti.  
  
### <a name="type-inference-with-named-types"></a>Inferenza del tipo con tipi denominati  
 È possibile ridurre il codice per la dichiarazione di `cust1` combinando gli inizializzatori di oggetto e l'inferenza del tipo locale. In questo modo è possibile omettere il `As` clausola nella dichiarazione di variabile. Il tipo di dati della variabile viene dedotto dal tipo dell'oggetto che viene creato dall'assegnazione. Nell'esempio seguente, il tipo della `cust6` è `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a>Note sui tipi denominati  
  
- Impossibile inizializzare un membro di classe più di una volta nell'elenco di inizializzatori di oggetto. La dichiarazione di `cust7` provoca un errore.  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- Un membro è utilizzabile per inizializzare se stesso o un altro campo. Se un membro viene eseguito prima che sia stato inizializzato, come illustrato nella seguente dichiarazione per `cust8`, verrà utilizzato il valore predefinito. Tenere presente che, quando viene elaborata una dichiarazione che usa un inizializzatore di oggetto, la prima cosa che accade è che viene richiamato il costruttore appropriato. Successivamente, vengono inizializzati i singoli campi nell'elenco di inizializzatori. Negli esempi seguenti, il valore predefinito per `Name` viene assegnato per `cust8`, e viene assegnato un valore inizializzato `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     L'esempio seguente usa il costruttore con parametri dalla `cust3` e `cust4` dichiarare e inizializzare `cust10` e `cust11`.  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- Gli inizializzatori di oggetto possono essere annidati. Nell'esempio riportato di seguito `AddressClass` è una classe che ha due proprietà, `City` e `State`e il `Customer` classe dispone di un `Address` proprietà che è un'istanza di `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- Elenco di inizializzazione non può essere vuoto.  
  
- L'istanza in fase di inizializzazione non può essere di tipo Object.  
  
- I membri di classe in fase di inizializzazione non possono essere membri condivisi, i membri di sola lettura, costanti o chiamate al metodo.  
  
- I membri della classe in fase di inizializzazione non può essere indicizzato o completo. Negli esempi seguenti generano errori del compilatore:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Tipi anonimi  
 I tipi anonimi di usare gli inizializzatori di oggetto per creare istanze dei nuovi tipi che non si definisce in modo esplicito e il nome. Al contrario, il compilatore genera un tipo in base alle proprietà che te nell'elenco di inizializzatori di oggetto. Poiché il nome del tipo non è specificato, viene considerato un *tipo anonimo*. Ad esempio, confrontare la seguente dichiarazione di quella precedente per `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 L'unica differenza è sintatticamente che viene specificato alcun nome dopo `New` per il tipo di dati. Tuttavia, ciò che accade è piuttosto diverso. Il compilatore definisce un tipo anonimo nuovo che ha due proprietà, `Name` e `City`e ne crea un'istanza con i valori specificati. L'inferenza del tipo determina i tipi di `Name` e `City` nell'esempio per essere stringhe.  
  
> [!CAUTION]
>  Il nome del tipo anonimo viene generato dal compilatore e può variare da compilazione a compilazione. Il codice deve usare o si basano sul nome di un tipo anonimo.  
  
 Poiché il nome del tipo non è disponibile, è possibile utilizzare un `As` clausola dichiarare `cust13`. Il tipo deve essere dedotto. Non si usa l'associazione tardiva, questo riduce l'utilizzo di tipi anonimi a variabili locali.  
  
 I tipi anonimi forniscono il supporto fondamentale per [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query. Per altre informazioni sull'utilizzo di tipi anonimi nelle query, vedere [i tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) e [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Note sui tipi anonimi  
  
- Sarà in genere tutti o la maggior parte delle proprietà in una dichiarazione di tipo anonimo alle proprietà chiave indicati digitando la parola chiave `Key` davanti al nome di proprietà.  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     Per altre informazioni sulle proprietà di chiave, vedere [chiave](../../../../visual-basic/language-reference/modifiers/key.md).  
  
- Come i tipi denominati, gli elenchi di inizializzatori per le definizioni di tipo anonimo devono dichiarare almeno una proprietà.  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- Quando viene dichiarata un'istanza di un tipo anonimo, il compilatore genera una definizione di tipo anonimo corrispondente. I nomi e tipi di dati delle proprietà vengono eseguiti dalla dichiarazione dell'istanza e sono inclusi dal compilatore nella definizione. Le proprietà non sono denominate e definite in anticipo, come avviene per un tipo denominato. I tipi vengono dedotti. È possibile specificare i tipi di dati delle proprietà usando un `As` clausola.  
  
- I tipi anonimi possono anche definire i nomi e valori delle relative proprietà in diversi altri modi. Ad esempio, una proprietà di tipo anonimo può richiedere il nome e il valore di una variabile o il nome e il valore di una proprietà di un altro oggetto.  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     Per altre informazioni sulle opzioni per la definizione delle proprietà in tipi anonimi, vedere [come: In grado di dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>Vedere anche

- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Procedura: Dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
- [Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
