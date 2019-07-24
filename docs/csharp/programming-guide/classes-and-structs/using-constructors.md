---
title: Uso dei costruttori - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 018710f753df261fce28e2e1cae1272b36923a05
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363014"
---
# <a name="using-constructors-c-programming-guide"></a>Utilizzo di costruttori (Guida per programmatori C#)

Quando si crea una [classe](../../../csharp/language-reference/keywords/class.md) o uno [struct](../../../csharp/language-reference/keywords/struct.md) viene chiamato il relativo costruttore. I costruttori hanno lo stesso nome della classe o dello struct e in genere inizializzano i membri dati del nuovo oggetto.  
  
 Nell'esempio seguente viene definita una classe denominata `Taxi` usando un costruttore semplice. Viene quindi creata un'istanza per la classe con l'operatore [new](../../../csharp/language-reference/operators/new-operator.md). Il costruttore `Taxi` viene richiamato dall'operatore `new` immediatamente dopo l'allocazione della memoria per il nuovo oggetto.  
  
 [!code-csharp[csProgGuideObjects#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#53)]  
  
 Un costruttore che non accetta parametri è detto *costruttore senza parametri*. I costruttori senza parametri vengono richiamati ogni volta che si crea un'istanza per un oggetto usando l'operatore `new` e non vengono specificati argomenti per `new`. Per altre informazioni, vedere [Costruttori di istanze](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 A meno che la classe non sia [statica](../../../csharp/language-reference/keywords/static.md), le classi senza costruttori ricevono un costruttore senza parametri pubblico dal compilatore C# perché possano creare istanze di classi. Per altre informazioni, vedere [Classi statiche e membri di classi statiche](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 È possibile impedire che venga creata un'istanza per una classe rendendo il costruttore privato, come indicato di seguito:  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 Per altre informazioni, vedere [Costruttori privati](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).  
  
 I costruttori per i tipi [struct](../../../csharp/language-reference/keywords/struct.md) sono simili ai costruttori di classi, ma gli `structs` non possono contenere un costruttore senza parametri esplicito poiché ne viene specificato automaticamente uno dal compilatore. Questo costruttore inizializza ogni campo dello `struct` sui valori predefiniti. Per altre informazioni, vedere [Tabella dei valori predefiniti](../../../csharp/language-reference/keywords/default-values-table.md). Il costruttore senza parametri viene tuttavia chiamato solo se si crea un'istanza dello `struct` con `new`. Questo codice, ad esempio, usa il costruttore senza parametri per <xref:System.Int32>, in modo da garantire che venga inizializzato l'Integer:  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 Il codice seguente, tuttavia, provoca un errore del compilatore perché non usa `new` e poiché tenta di usare un oggetto che non è stato inizializzato:  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 In alternativa, gli oggetti basati su `structs`, inclusi tutti i tipi numerici incorporati, possono essere inizializzati o assegnati e quindi usati come nell'esempio seguente:  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 La chiamata al costruttore senza parametri per un tipo di valore non è quindi necessaria.  
  
 Sia le classi che gli `structs` possono definire costruttori che accettano parametri. I costruttori che accettano parametri devono essere chiamati con un'istruzione `new` o un'istruzione di [base](../../../csharp/language-reference/keywords/base.md). Le classi e gli `structs` possono anche definire più costruttori. Né le une né gli altri devono necessariamente definire un costruttore senza parametri. Ad esempio:  
  
 [!code-csharp[csProgGuideObjects#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#54)]  
  
 Questa classe può essere creata usando una delle istruzioni seguenti:  
  
 [!code-csharp[csProgGuideObjects#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#55)]  
  
 Un costruttore può usare la parola chiave `base` per chiamare il costruttore di una classe di base. Ad esempio:  
  
 [!code-csharp[csProgGuideObjects#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#56)]  
  
 In questo esempio il costruttore per la classe di base viene chiamato prima che venga eseguito il blocco per il costruttore. La parola chiave `base` può essere usata con o senza parametri. Tutti i parametri per il costruttore possono essere usati come parametri per `base` o come parte di un'espressione. Per altre informazioni, vedere [base](../../../csharp/language-reference/keywords/base.md).  
  
 In una classe derivata, se un costruttore di classe base non viene chiamato in modo esplicito usando la parola chiave `base`, il costruttore senza parametri, se ne esiste uno, viene chiamato in modo implicito. Ciò significa quindi che le seguenti dichiarazioni del costruttore si equivalgono:  
  
 [!code-csharp[csProgGuideObjects#58](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#58)]  
  
 [!code-csharp[csProgGuideObjects#57](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#57)]  
  
 Se una classe di base non offre un costruttore senza parametri, la classe derivata deve effettuare una chiamata esplicita a un costruttore di base usando `base`.  
  
 Un costruttore può richiamare un altro costruttore nello stesso oggetto usando la parola chiave [this](../../../csharp/language-reference/keywords/this.md). Come `base`, `this` può essere utilizzata con o senza parametri e gli eventuali parametri nel costruttore sono disponibili come parametri per `this` o come parte di un'espressione. Ad esempio, il secondo costruttore nell'esempio precedente può essere riscritto usando `this`:  
  
 [!code-csharp[csProgGuideObjects#59](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#59)]  
  
 L'uso della parola chiave `this` nell'esempio precedente causa la chiamata di questo costruttore:  
  
 [!code-csharp[csProgGuideObjects#60](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#60)]  
  
 I costruttori possono essere contrassegnati come [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) o [private protected](../../../csharp/language-reference/keywords/private-protected.md). Questi modificatori di accesso definiscono il modo in cui gli utenti della classe possono costruire la classe. Per altre informazioni, vedere [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) (Modificatori di accesso).  
  
 Un costruttore può essere dichiarato statico usando la parola chiave [static](../../../csharp/language-reference/keywords/static.md). I costruttori statici vengono chiamati automaticamente subito prima dell'accesso ai campi statici e in genere vengono usati per inizializzare i membri delle classi statiche. Per altre informazioni, vedere [Costruttori statici](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## <a name="c-language-specification"></a>Specifiche del linguaggio C#  

Per altre informazioni, vedere [Costruttori di istanze](~/_csharplang/spec/classes.md#instance-constructors) e [Costruttori statici](~/_csharplang/spec/classes.md#static-constructors) in [Specifica del linguaggio C#](../../language-reference/language-specification/index.md). La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Costruttori](../../../csharp/programming-guide/classes-and-structs/constructors.md)
- [Finalizzatori](../../../csharp/programming-guide/classes-and-structs/destructors.md)
