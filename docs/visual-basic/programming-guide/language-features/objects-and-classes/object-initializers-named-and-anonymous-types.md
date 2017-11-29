---
title: 'Inizializzatori di oggetto: tipi denominati e tipi anonimi (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 349e4f7b4902eb18845fee7cb4d01b217849a4d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a>Inizializzatori di oggetto: tipi denominati e tipi anonimi (Visual Basic)
Gli inizializzatori di oggetto consentono di specificare le proprietà per un oggetto complesso usando un'unica espressione. Possono essere utilizzati per creare istanze di tipi denominati e tipi anonimi.  
  
## <a name="declarations"></a>Dichiarazioni  
 Le dichiarazioni di istanze di tipi denominati e anonimi possono apparire quasi identiche, ma non gli effetti sono uguali. Ogni categoria dispone di funzionalità e restrizioni di propri. Nell'esempio seguente viene illustrato un modo pratico per dichiarare e inizializzare un'istanza di una classe denominata, `Customer`, utilizzando un elenco di inizializzatori di oggetto. Si noti che il nome della classe viene specificato dopo la parola chiave `New`.  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 Un tipo anonimo ha un nome utilizzabile. Pertanto, creazione di un'istanza di un tipo anonimo non può includere un nome di classe.  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 I requisiti e i risultati delle due dichiarazioni non sono uguali. Per `namedCust`, `Customer` classe che ha un `Name` proprietà deve esistere già e la dichiarazione crea un'istanza di tale classe. Per `anonymousCust`, il compilatore definisce una nuova classe che ha una proprietà, una stringa definita `Name`e crea una nuova istanza della classe.  
  
## <a name="named-types"></a>Tipi denominati  
 Gli inizializzatori di oggetto forniscono un modo semplice per chiamare il costruttore di un tipo e quindi impostare i valori di alcune o tutte le proprietà in una singola istruzione. Il compilatore richiama il costruttore appropriato per l'istruzione: il costruttore predefinito, se viene presentato alcun argomento o un costruttore con parametri, se vengono inviati uno o più argomenti. Successivamente, le proprietà specificate vengono inizializzate nell'ordine in cui vengono presentati nell'elenco di inizializzatori.  
  
 Ogni inizializzazione nell'elenco di inizializzatori è costituito dall'assegnazione di un valore iniziale a un membro della classe. I nomi e tipi di dati dei membri vengono determinati quando la classe è definita. Negli esempi seguenti, il `Customer` classe deve esistere e devono avere membri denominati `Name` e `City` che possono accettare valori stringa.  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 In alternativa, è possibile ottenere lo stesso risultato utilizzando il codice seguente:  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 Ognuna di queste dichiarazioni è equivalente all'esempio seguente, che consente di creare un `Customer` oggetto utilizzando il costruttore predefinito e specifica i valori iniziali per il `Name` e `City` proprietà tramite un `With` istruzione.  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 Se il `Customer` classe contiene un costruttore con parametri che consente di inviare un valore per `Name`, ad esempio, è possibile anche dichiarare e inizializzare un `Customer` oggetto nei modi seguenti:  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 Non è necessario inizializzare tutte le proprietà, come illustrato nel codice seguente.  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 Tuttavia, l'elenco di inizializzazione non può essere vuoto. Le proprietà non inizializzate mantengono i valori predefiniti.  
  
### <a name="type-inference-with-named-types"></a>Inferenza del tipo con tipi denominati  
 È possibile ridurre il codice per la dichiarazione di `cust1` combinando gli inizializzatori di oggetto e l'inferenza del tipo locale. In questo modo è possibile omettere il `As` clausola nella dichiarazione di variabile. Il tipo di dati della variabile viene dedotto dal tipo dell'oggetto creato dall'assegnazione. Nell'esempio seguente, il tipo di `cust6` è `Customer`.  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a>Note sui tipi denominati  
  
-   Impossibile inizializzare un membro di classe più di una volta nell'elenco di inizializzatori di oggetto. La dichiarazione di `cust7` causa un errore.  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   Un membro è utilizzabile per inizializzare se stesso o un altro campo. Se si accede a un membro prima che sia stato inizializzato, come illustrato nella seguente dichiarazione per `cust8`, verrà utilizzato il valore predefinito. Tenere presente che quando viene elaborata una dichiarazione che utilizza un inizializzatore di oggetto, il primo elemento che si verifica se viene richiamato il costruttore appropriato. Successivamente, vengono inizializzati i singoli campi nell'elenco di inizializzatori. Negli esempi seguenti, il valore predefinito per `Name` viene assegnato per `cust8`, e viene assegnato un valore inizializzato `cust9`.  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     Nell'esempio seguente viene utilizzato il costruttore con parametri da `cust3` e `cust4` per dichiarare e inizializzare `cust10` e `cust11`.  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   Gli inizializzatori di oggetto possono essere nidificati. Nell'esempio seguente, `AddressClass` è una classe che ha due proprietà, `City` e `State`e `Customer` classe dispone di un `Address` proprietà che è un'istanza di `AddressClass`.  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   Elenco di inizializzazione non può essere vuoto.  
  
-   L'istanza viene inizializzata non può essere di tipo Object.  
  
-   Membri condivisi, i membri di sola lettura, costanti o chiamate al metodo, non possono essere membri di classe da inizializzare.  
  
-   Fase di inizializzazione non può essere indicizzato o completo di membri della classe. Negli esempi seguenti generano errori del compilatore:  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a>Tipi anonimi  
 Tipi anonimi usare gli inizializzatori di oggetto per creare istanze dei nuovi tipi che non si definisce in modo esplicito e il nome. Al contrario, il compilatore genera un tipo in base alle proprietà che scelto nell'elenco di inizializzatori di oggetto. Poiché il nome del tipo non è specificato, viene considerato un *tipo anonimo*. Ad esempio, confrontare la seguente dichiarazione di quella precedente per `cust6`.  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 L'unica differenza è la sintassi che è stato specificato alcun nome dopo `New` per il tipo di dati. Cosa accade è piuttosto diversa. Il compilatore definisce un nuovo tipo anonimo che ha due proprietà, `Name` e `City`e crea un'istanza con i valori specificati. L'inferenza del tipo determina i tipi di `Name` e `City` nell'esempio per essere stringhe.  
  
> [!CAUTION]
>  Il nome del tipo anonimo viene generato dal compilatore e può variare da compilazione a compilazione. Il codice non deve usare o basarsi sul nome di un tipo anonimo.  
  
 Poiché il nome del tipo non è disponibile, è possibile utilizzare un `As` clausola per dichiarare `cust13`. Il tipo deve essere dedotto. Senza utilizzare l'associazione tardiva, limita l'utilizzo di tipi anonimi alle variabili locali.  
  
 Tipi anonimi forniscono supporto critico per [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query. Per ulteriori informazioni sull'utilizzo di tipi anonimi nelle query, vedere [tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) e [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
### <a name="remarks-about-anonymous-types"></a>Note sui tipi anonimi  
  
-   Tutte o la maggior parte delle proprietà in una dichiarazione di tipo anonimo saranno generalmente proprietà chiave, indicate digitando la parola chiave `Key` davanti al nome di proprietà.  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     Per ulteriori informazioni sulle proprietà chiave, vedere [chiave](../../../../visual-basic/language-reference/modifiers/key.md).  
  
-   Come i tipi denominati, gli elenchi di inizializzatori per definizioni di tipo anonimo devono dichiarare almeno una proprietà.  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   Quando viene dichiarata un'istanza di un tipo anonimo, il compilatore genera una definizione di tipo anonimo corrispondente. I nomi e tipi di dati delle proprietà provengono dalla dichiarazione dell'istanza e sono inclusi dal compilatore nella definizione. Le proprietà non sono denominate e definite in precedenza, come avviene per un tipo denominato. I tipi inferiti. È possibile specificare i tipi di dati delle proprietà utilizzando un `As` clausola.  
  
-   Tipi anonimi possono anche definire i nomi e i valori delle relative proprietà in diversi altri modi. Ad esempio, una proprietà di tipo anonimo può richiedere il nome e il valore di una variabile o il nome e valore di una proprietà di un altro oggetto.  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     Per ulteriori informazioni sulle opzioni per la definizione delle proprietà nei tipi anonimi, vedere [procedura: dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Procedura: Dedurre tipi e nomi di proprietà nelle dichiarazioni di tipo anonimo](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)  
 [Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
