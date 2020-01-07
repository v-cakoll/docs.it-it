---
title: 'Inizializzatori di oggetto: tipi denominati e tipi anonimi'
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
ms.openlocfilehash: e6ffc649d7eb841c2d009b0ec1237975f46e2d2d
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636809"
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Inizializzatori di oggetto: tipi denominati e tipi anonimi (Visual Basic)
Gli inizializzatori di oggetto consentono di specificare le proprietà per un oggetto complesso utilizzando una singola espressione. Possono essere usati per creare istanze di tipi denominati e di tipi anonimi.  
  
## <a name="declarations"></a>Dichiarazioni  
 Le dichiarazioni di istanze di tipi denominati e anonimi possono apparire quasi identiche, ma gli effetti non sono uguali. Ogni categoria presenta le funzionalità e le restrizioni. Nell'esempio seguente viene illustrato un modo pratico per dichiarare e inizializzare un'istanza di una classe denominata, `Customer`, utilizzando un elenco di inizializzatori di oggetto. Si noti che il nome della classe viene specificato dopo la parola chiave `New`.  
  
 [!code-vb[VbVbalrObjectInit#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#1)]  
  
 Un tipo anonimo non ha un nome utilizzabile. Pertanto, una creazione di un'istanza di un tipo anonimo non può includere un nome di classe.  
  
 [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
 I requisiti e i risultati delle due dichiarazioni non sono uguali. Per `namedCust`, una classe `Customer` che dispone di una proprietà `Name` deve esistere già e la dichiarazione crea un'istanza di tale classe. Per `anonymousCust`, il compilatore definisce una nuova classe con una proprietà, una stringa denominata `Name`e crea una nuova istanza di tale classe.  
  
## <a name="named-types"></a>Tipi denominati  
 Gli inizializzatori di oggetto forniscono un modo semplice per chiamare il costruttore di un tipo e quindi impostare i valori di alcune o tutte le proprietà in una singola istruzione. Il compilatore richiama il costruttore appropriato per l'istruzione: il costruttore senza parametri se non vengono presentati argomenti o un costruttore con parametri se vengono inviati uno o più argomenti. Successivamente, le proprietà specificate vengono inizializzate nell'ordine in cui sono visualizzate nell'elenco di inizializzatori.  
  
 Ogni inizializzazione nell'elenco di inizializzatori è costituita dall'assegnazione di un valore iniziale a un membro della classe. I nomi e i tipi di dati dei membri vengono determinati quando la classe è definita. Negli esempi seguenti la classe `Customer` deve esistere e deve avere membri denominati `Name` e `City` che possono accettare valori di stringa.  
  
 [!code-vb[VbVbalrObjectInit#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#3)]  
  
 In alternativa, è possibile ottenere lo stesso risultato usando il codice seguente:  
  
 [!code-vb[VbVbalrObjectInit#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#4)]  
  
 Ognuna di queste dichiarazioni equivale all'esempio seguente, che crea un oggetto `Customer` usando il costruttore senza parametri, quindi specifica i valori iniziali per le proprietà `Name` e `City` usando un'istruzione `With`.  
  
 [!code-vb[VbVbalrObjectInit#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#5)]  
  
 Se la classe `Customer` contiene un costruttore con parametri che consente di inviare un valore per `Name`, ad esempio, è anche possibile dichiarare e inizializzare un oggetto `Customer` nei modi seguenti:  
  
 [!code-vb[VbVbalrObjectInit#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#6)]  
  
 Non è necessario inizializzare tutte le proprietà, come illustrato nel codice seguente.  
  
 [!code-vb[VbVbalrObjectInit#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#7)]  
  
 Tuttavia, l'elenco di inizializzazione non può essere vuoto. Le proprietà non inizializzate mantengono i valori predefiniti.  
  
### <a name="type-inference-with-named-types"></a>Inferenza del tipo con i tipi denominati  
 È possibile abbreviare il codice per la dichiarazione di `cust1` combinando gli inizializzatori di oggetto e l'inferenza del tipo locale. In questo modo è possibile omettere la clausola `As` nella dichiarazione di variabile. Il tipo di dati della variabile viene dedotto dal tipo dell'oggetto creato dall'assegnazione. Nell'esempio seguente, il tipo di `cust6` è `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#8)]  
  
### <a name="remarks-about-named-types"></a>Osservazioni sui tipi denominati  
  
- Un membro di classe non può essere inizializzato più di una volta nell'elenco di inizializzatori di oggetto. La dichiarazione di `cust7` causa un errore.  
  
     [!code-vb[VbVbalrObjectInit#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#9)]  
  
- Un membro può essere utilizzato per inizializzare se stesso o un altro campo. Se si accede a un membro prima che sia stato inizializzato, come nella dichiarazione seguente per `cust8`, verrà utilizzato il valore predefinito. Tenere presente che quando viene elaborata una dichiarazione che usa un inizializzatore di oggetto, la prima cosa che accade è che viene richiamato il costruttore appropriato. Successivamente, i singoli campi nell'elenco di inizializzatori vengono inizializzati. Negli esempi seguenti viene assegnato il valore predefinito per `Name` per `cust8`e viene assegnato un valore inizializzato in `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#10)]  
  
     Nell'esempio seguente viene usato il costruttore con parametri da `cust3` e `cust4` per dichiarare e inizializzare `cust10` e `cust11`.  
  
     [!code-vb[VbVbalrObjectInit#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#11)]  
  
- Gli inizializzatori di oggetto possono essere annidati. Nell'esempio seguente `AddressClass` è una classe che dispone di due proprietà, `City` e `State`e la classe `Customer` ha una proprietà `Address` che è un'istanza di `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#12)]  
  
- L'elenco di inizializzazione non può essere vuoto.  
  
- L'istanza da inizializzare non può essere di tipo Object.  
  
- I membri della classe inizializzati non possono essere membri condivisi, membri di sola lettura, costanti o chiamate al metodo.  
  
- I membri della classe inizializzati non possono essere indicizzati o qualificati. Gli esempi seguenti generano errori del compilatore:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Tipi anonimi  
 I tipi anonimi usano gli inizializzatori di oggetto per creare istanze di nuovi tipi che non vengono definiti e denominati in modo esplicito. Al contrario, il compilatore genera un tipo in base alle proprietà designate nell'elenco di inizializzatori di oggetto. Poiché il nome del tipo non è specificato, viene definito come *tipo anonimo*. Ad esempio, confrontare la seguente dichiarazione con quella precedente per `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#13)]  
  
 L'unica differenza sintatticamente è che non viene specificato alcun nome dopo `New` per il tipo di dati. Tuttavia, ciò che accade è piuttosto diverso. Il compilatore definisce un nuovo tipo anonimo che dispone di due proprietà, `Name` e `City`, e ne crea un'istanza con i valori specificati. L'inferenza del tipo determina i tipi di `Name` e `City` nell'esempio in modo che siano stringhe.  
  
> [!CAUTION]
> Il nome del tipo anonimo viene generato dal compilatore e può variare dalla compilazione alla compilazione. Il codice non deve usare o basarsi sul nome di un tipo anonimo.  
  
 Poiché il nome del tipo non è disponibile, non è possibile usare una clausola `As` per dichiarare `cust13`. Il tipo deve essere dedotto. Senza usare l'associazione tardiva, questo limita l'uso di tipi anonimi alle variabili locali.  
  
 I tipi anonimi forniscono supporto critico per le query LINQ. Per ulteriori informazioni sull'utilizzo di tipi anonimi nelle query, vedere [tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) e [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Osservazioni sui tipi anonimi  
  
- In genere, tutte o la maggior parte delle proprietà in una dichiarazione di tipo anonimo saranno proprietà chiave, indicate digitando la parola chiave `Key` davanti al nome della proprietà.  
  
     [!code-vb[VbVbalrObjectInit#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#14)]  
  
     Per ulteriori informazioni sulle proprietà chiave, vedere [Key](../../../../visual-basic/language-reference/modifiers/key.md).  
  
- Come i tipi denominati, gli elenchi di inizializzatori per le definizioni di tipi anonimi devono dichiarare almeno una proprietà.  
  
     [!code-vb[VbVbalrObjectInit#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#2)]  
  
- Quando viene dichiarata un'istanza di un tipo anonimo, il compilatore genera una definizione di tipo anonimo corrispondente. I nomi e i tipi di dati delle proprietà vengono ricavati dalla dichiarazione dell'istanza e sono inclusi dal compilatore nella definizione. Le proprietà non sono denominate e definite in anticipo, come per un tipo denominato. I tipi vengono dedotti. Non è possibile specificare i tipi di dati delle proprietà utilizzando una clausola `As`.  
  
- I tipi anonimi possono anche definire i nomi e i valori delle rispettive proprietà in diversi altri modi. Ad esempio, una proprietà di tipo anonimo può assumere sia il nome che il valore di una variabile oppure il nome e il valore di una proprietà di un altro oggetto.  
  
     [!code-vb[VbVbalrObjectInit#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class1.vb#15)]  
  
     Per altre informazioni sulle opzioni per la definizione delle proprietà nei tipi anonimi, vedere [procedura: dedurre i nomi e i tipi delle proprietà nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>Vedere anche

- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Procedura: Dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
- [Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
