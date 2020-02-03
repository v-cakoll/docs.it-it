---
title: Tipi - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- value types [C#]
- reference types [C#]
- types [C#]
- C# language, data types
- common type system [C#]
- data types [C#]
- C# language, types
- strong typing [C#]
ms.assetid: f782d7cc-035e-4500-b1b1-36a9881130ad
ms.openlocfilehash: be2af77f9680ab3285720525638bba8ef2041999
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745371"
---
# <a name="types-c-programming-guide"></a>Tipi (Guida per programmatori C#)

## <a name="types-variables-and-values"></a>Tipi, variabili e valori

C# è un linguaggio fortemente tipizzato. Ogni variabile e costante ha un tipo, così come ogni espressione che restituisce un valore. Ogni firma del metodo specifica un tipo per ogni parametro di input e per il valore restituito. La libreria di classi .NET definisce un set di tipi numerici predefiniti, nonché tipi più complessi che rappresentano un'ampia gamma di costrutti logici, ad esempio il file system, le connessioni di rete, le raccolte e matrici di oggetti e le date. Un tipico programma C# usa tipi dalla libreria di classi e tipi definiti dall'utente che modellano i concetti specifici del dominio relativo al problema del programma.

Le informazioni archiviate in un tipo possono includere quanto segue:

- Lo spazio di archiviazione richiesto da una variabile del tipo.

- I valori minimi e massimi che può rappresentare.

- I membri (metodi, campi, eventi e così via) in esso contenuti.

- Il tipo di base da cui eredita.

- Il percorso in cui viene allocata la memoria per le variabili in fase di esecuzione.

- I tipi di operazioni consentite.

Il compilatore usa le informazioni sul tipo per assicurarsi che tutte le operazioni eseguite nel codice siano *indipendenti dai tipi*. Se ad esempio si dichiara una variabile di tipo [int](../../language-reference/builtin-types/integral-numeric-types.md), il compilatore consente di usare la variabile anche in operazioni di addizione e sottrazione. Se si prova a eseguire le stesse operazioni su una variabile di tipo [bool](../../language-reference/builtin-types/bool.md), il compilatore genera un errore, come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideTypes#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#42)]

> [!NOTE]
> Gli sviluppatori C e C++ devono tenere presente che in C#, [bool](../../language-reference/builtin-types/bool.md) non è convertibile in [int](../../language-reference/builtin-types/integral-numeric-types.md).

Il compilatore incorpora le informazioni sul tipo nel file eseguibile come metadati. Common Language Runtime (CLR) usa i metadati in fase di esecuzione per garantire ulteriormente l'indipendenza dai tipi quando alloca e recupera la memoria.

### <a name="specifying-types-in-variable-declarations"></a>Specifica dei tipi nelle dichiarazioni di variabile

Quando si dichiara una variabile o costante in un programma, è necessario specificarne il tipo oppure usare la parola chiave [var](../../language-reference/keywords/var.md) per consentire al compilatore di dedurre il tipo. L'esempio seguente illustra alcune dichiarazioni di variabili che usano entrambi i tipi numerici predefiniti e i tipi complessi definiti dall'utente:

[!code-csharp[csProgGuideTypes#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#36)]

I tipi di parametri del metodo e valori restituiti sono specificati nella firma del metodo. La firma seguente illustra un metodo che richiede un [int](../../language-reference/builtin-types/integral-numeric-types.md) come argomento di input e restituisce una stringa:

[!code-csharp[csProgGuideTypes#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#35)]

Una variabile dichiarata non può essere dichiarata di nuovo con un tipo nuovo e non è possibile assegnarle un valore che non è compatibile con il relativo tipo dichiarato. Ad esempio, non è possibile dichiarare un valore [int](../../language-reference/builtin-types/integral-numeric-types.md) e quindi assegnargli un valore booleano di `true`. I valori possono tuttavia essere convertiti in altri tipi, ad esempio quando vengono assegnati a nuove variabili o passati come argomenti di metodo. Una *conversione del tipo* che non causa la perdita di dati viene eseguita automaticamente dal compilatore, Una conversione che potrebbe causare la perdita di dati richiede un *cast* nel codice sorgente.

Per altre informazioni, vedere [Cast e conversioni di tipi](./casting-and-type-conversions.md).

## <a name="built-in-types"></a>Tipi incorporati

Il linguaggio C# offre un set standard di tipi numerici predefiniti per rappresentare numeri interi, valori a virgola mobile, espressioni booleane, caratteri di testo, valori decimali e altri tipi di dati. Sono anche disponibili tipi `string` e `object` incorporati, che possono essere usati in qualsiasi programma C#. Per altre informazioni sui tipi incorporati, vedere [Reference Tables for built-in Types](../../language-reference/keywords/built-in-types-table.md) (Tabelle di riferimento per i tipi incorporati).

## <a name="custom-types"></a>Tipi personalizzati

Usare i costrutti [struct](../../language-reference/keywords/struct.md), [class](../../language-reference/keywords/class.md), [interface](../../language-reference/keywords/interface.md) e [enum](../../language-reference/builtin-types/enum.md) per creare tipi personalizzati. La libreria di classi .NET stessa è una raccolta di tipi personalizzati offerti da Microsoft che è possibile usare nelle proprie applicazioni. Per impostazione predefinita, i tipi più comunemente usati nella libreria di classi sono disponibili in qualsiasi programma C#, mentre altri diventano disponibili solo quando si aggiunge in modo esplicito un riferimento di progetto all'assembly in cui sono definiti. Dopo che il compilatore avrà un riferimento all'assembly, è possibile dichiarare variabili (e costanti) dei tipi dichiarati in tale assembly in codice sorgente. Per altre informazioni, vedere [Libreria di classi .NET](../../../standard/class-library-overview.md).

## <a name="the-common-type-system"></a>Common Type System

È importante tenere presente due aspetti fondamentali del sistema dei tipi in .NET:

- Il tipo supporta il principio di ereditarietà. I tipi possono derivare da altri tipi, denominati *tipi di base*. Il tipo derivato eredita (con alcune limitazioni) metodi, proprietà e altri membri del tipo di base, Il tipo di base può a sua volta derivare da un altro tipo, nel quale caso il tipo derivato eredita i membri di entrambi i tipi di base nella gerarchia di ereditarietà. Tutti i tipi, inclusi i tipi numerici predefiniti, ad esempio <xref:System.Int32?displayProperty=nameWithType> (parola chiave C#: [int](../../language-reference/builtin-types/integral-numeric-types.md)), derivano in definitiva da un unico tipo di base, ovvero <xref:System.Object?displayProperty=nameWithType> (parola chiave C#: [object](../../language-reference/builtin-types/reference-types.md)). Questa gerarchia di tipi unificata prende il nome di [Common Type System](../../../standard/base-types/common-type-system.md) (CTS). Per altre informazioni sull'ereditarietà in C#, vedere [Ereditarietà](../classes-and-structs/inheritance.md).

- Nel CTS ogni tipo è definito come *tipo valore* o *tipo riferimento*. In queste due categorie sono inclusi anche tutti i tipi personalizzati nella libreria di classi .NET e i tipi definiti dall'utente. I tipi definiti tramite la parola chiave [struct](../../language-reference/keywords/struct.md) sono tipi valore e tutti i tipi numerici incorporati sono tipi `structs`. I tipi definiti tramite la parola chiave [class](../../language-reference/keywords/class.md) sono tipi di riferimento. I tipi riferimento e i tipi valore hanno regole diverse in fase di compilazione e un comportamento diverso in fase di esecuzione.

La figura seguente illustra la relazione tra tipi valore e tipi riferimento nel CTS.

L'immagine seguente illustra tipi valore e tipi riferimento nel CTS:

![Screenshot che illustra i tipi valore e i tipi riferimento nel CTS.](./media/index/value-reference-types-common-type-system.png)

> [!NOTE]
> È possibile osservare come i tipi usati con maggiore frequenza siano tutti organizzati nello spazio dei nomi <xref:System>. L'inserimento di un tipo in uno spazio dei nomi, tuttavia, è indipendente dalla categoria a cui appartiene il tipo.

### <a name="value-types"></a>Tipi valore

I tipi valore derivano da <xref:System.ValueType?displayProperty=nameWithType>, che deriva da <xref:System.Object?displayProperty=nameWithType>. I tipi che derivano da <xref:System.ValueType?displayProperty=nameWithType> hanno un comportamento speciale in CLR. Le variabili dei tipi valore contengono direttamente i rispettivi valori, ovvero la memoria viene allocata inline nel contesto in cui è dichiarata la variabile. Non esiste un'allocazione heap o un overhead di Garbage Collection separato per le variabili dei tipi valore.

Esistono due categorie di tipi valore: [struct](../../language-reference/keywords/struct.md) e [enum](../../language-reference/builtin-types/enum.md).

I tipi numerici incorporati sono struct, i cui metodi e proprietà sono accessibili dall'utente:

```csharp
// Static method on type byte.
byte b = byte.MaxValue;
```

Ad essi, tuttavia, si dichiarano e si assegnano valori come se fossero tipi non aggregati semplici:

```csharp
byte num = 0xA;
int i = 5;
char c = 'Z';
```

I tipi valore sono *sealed*, ovvero non è possibile, ad esempio, derivare un tipo da <xref:System.Int32?displayProperty=nameWithType> e non è possibile definire uno struct da ereditare da uno struct o una classe definita dall'utente, poiché uno struct può ereditare solo da <xref:System.ValueType?displayProperty=nameWithType>. Uno struct può implementare tuttavia una o più interfacce. È possibile eseguire il cast di un tipo struct in qualsiasi tipo di interfaccia implementata. Questa operazione genera tuttavia una *conversione boxing*  per eseguire il wrapping dello struct in un oggetto tipo riferimento sull'heap gestito. Le operazioni di conversione boxing si verificano quando si passa un tipo valore a un metodo che accetta <xref:System.Object?displayProperty=nameWithType> o qualsiasi tipo di interfaccia come parametro di input. Per altre informazioni, vedere [Boxing e unboxing](./boxing-and-unboxing.md).

Usare la parola chiave [struct](../../language-reference/keywords/struct.md) per creare tipi valore personalizzati. In genere, uno struct viene usato come contenitore per un piccolo set di variabili correlate, come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideObjects#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#1)]

Per altre informazioni sui tipi struct, vedere [Struct](../classes-and-structs/structs.md). Per ulteriori informazioni sui tipi di valore, vedere [tipi di valore](../../language-reference/builtin-types/value-types.md).

L'altra categoria di tipi valore è [enum](../../language-reference/builtin-types/enum.md). Un tipo enum definisce un set di costanti integrali denominate. L'enumerazione <xref:System.IO.FileMode?displayProperty=nameWithType> nella libreria di classi .NET, ad esempio, contiene un set di valori interi costanti e denominati che specificano come deve essere aperto un file. L'enumerazione deve essere definita come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideTypes#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#44)]

Il valore della costante `System.IO.FileMode.Create` è 2. I nomi, tuttavia, sono molto più significativi per gli utenti che leggono il codice sorgente e, quindi, è preferibile usare enumerazioni anziché valori letterali numerici costanti. Per altre informazioni, vedere <xref:System.IO.FileMode?displayProperty=nameWithType>.

Tutte le enumerazioni ereditano da <xref:System.Enum?displayProperty=nameWithType>, che eredita da <xref:System.ValueType?displayProperty=nameWithType>. Tutte le regole valide per i tipi struct sono valide anche per le enumerazioni. Per altre informazioni sulle enumerazioni, vedere [tipi di enumerazione](../../language-reference/builtin-types/enum.md).

### <a name="reference-types"></a>Tipi di riferimento

Un tipo definito come [classe](../../language-reference/keywords/class.md), [delegato](../../language-reference/builtin-types/reference-types.md), matrice o [interfaccia](../../language-reference/keywords/interface.md) è un *tipo riferimento*. In fase di esecuzione, quando si dichiara una variabile di un tipo riferimento, la variabile contiene il valore [null](../../language-reference/keywords/null.md) fino a quando non si crea in modo esplicito un oggetto usando l'operatore [new](../../language-reference/operators/new-operator.md) o fino a quando non le viene assegnato un oggetto creato altrove tramite `new`, come illustrato nell'esempio seguente:

```csharp
MyClass mc = new MyClass();
MyClass mc2 = mc;
```

Un'interfaccia deve essere inizializzata insieme a un oggetto classe che la implementa. Se `MyClass` implementa `IMyInterface`, si crea un'istanza di `IMyInterface`, come illustrato nell'esempio seguente:

```csharp
IMyInterface iface = new MyClass();
```

Quando viene creato l'oggetto, la memoria viene allocata nell'heap gestito e la variabile mantiene solo un riferimento al percorso dell'oggetto. I tipi nell'heap gestito richiedono un overhead quando vengono allocati e recuperati dalla funzionalità di gestione automatica della memoria di CLR, nota come *Garbage Collection*. La Garbage Collection, tuttavia, è anche altamente ottimizzata e, nella maggior parte degli scenari, non genera un problema di prestazioni. Per altre informazioni sulla Garbage Collection, vedere [Gestione automatica della memoria](../../../standard/automatic-memory-management.md).

Tutte le matrici sono tipi riferimento, anche se i relativi elementi sono tipi valore. Le matrici derivano in modo implicito dalla classe <xref:System.Array?displayProperty=nameWithType>, ma vengono dichiarate e usate con la sintassi semplificata fornita da C#, come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideTypes#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#45)]

I tipi riferimento supportano completamente l'ereditarietà. Quando si crea una classe, è possibile ereditare da qualsiasi altra interfaccia o classe che non è definita come [sealed](../../language-reference/keywords/sealed.md), e altre classi possono ereditare dalla classe ed eseguire l'override dei metodi virtuali. Per altre informazioni su come creare classi personalizzate, vedere [Classi e struct](../classes-and-structs/index.md). Per altre informazioni sull'ereditarietà e sui metodi virtuali, vedere [Ereditarietà](../classes-and-structs/inheritance.md).

## <a name="types-of-literal-values"></a>Tipi di valori letterali

In C# i valori letterali ricevono un tipo dal compilatore. È possibile specificare come deve essere tipizzato un valore letterale numerico aggiungendo una lettera alla fine del numero. Per specificare, ad esempio, che il valore 4.56 deve essere considerato come un tipo float, aggiungere una "f" o una "F" dopo il numero: `4.56f`. Se non viene aggiunta alcuna lettera, il compilatore dedurrà un tipo per il valore letterale. Per ulteriori informazioni sui tipi che è possibile specificare con i suffissi di lettera, vedere [tipi numerici integrali](../../language-reference/builtin-types/integral-numeric-types.md) e [tipi numerici a virgola mobile](../../language-reference/builtin-types/floating-point-numeric-types.md).

Poiché i valori letterali sono tipizzati e tutti i tipi derivano in ultima istanza da <xref:System.Object?displayProperty=nameWithType>, è possibile scrivere e compilare codice come il seguente:

[!code-csharp[csProgGuideTypes#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#37)]

## <a name="generic-types"></a>Tipi generici

Un tipo può essere dichiarato con uno o più *parametri di tipo* che fungono da segnaposto per il tipo effettivo (*tipo concreto*) che il codice client specifica quando si crea un'istanza del tipo. Tali tipi sono definiti *tipi generici*. Ad esempio, il tipo .NET <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> dispone di un parametro di tipo a cui per convenzione viene assegnato il nome *t*. Quando si crea un'istanza del tipo, si specifica il tipo degli oggetti che l'elenco conterrà, ad esempio, String:

```csharp
List<string> stringList = new List<string>();
stringList.Add("String example");
// compile time error adding a type other than a string:
stringList.Add(4);
```

L'uso del parametro di tipo rende possibile il riuso della stessa classe per contenere qualsiasi tipo di elemento, senza la necessità di convertire ogni elemento in [object](../../language-reference/builtin-types/reference-types.md). Le classi di raccolte generiche sono definite *raccolte fortemente tipizzate* perché il compilatore conosce il tipo specifico degli elementi della raccolta e può generare un errore in fase di compilazione se, ad esempio, si prova ad aggiungere un numero intero all'oggetto `stringList` nell'esempio precedente. Per altre informazioni, vedere [Generics](../generics/index.md).

## <a name="implicit-types-anonymous-types-and-nullable-value-types"></a>Tipi impliciti, tipi anonimi e tipi di valore Nullable

Come indicato in precedenza, è possibile digitare una variabile locale in modo implicito usando la parola chiave [var](../../language-reference/keywords/var.md). A tale variabile viene comunque assegnato un tipo in fase di compilazione, ma il tipo viene specificato dal compilatore. Per altre informazioni, vedere [Variabili locali tipizzate in modo implicito](../classes-and-structs/implicitly-typed-local-variables.md).

In alcuni casi non è consigliabile creare un tipo denominato per set semplici di valori correlati che non si intende archiviare o passare fuori dai limiti del metodo. A questo scopo è possibile creare *tipi anonimi*. Per altre informazioni, vedere [Tipi anonimi](../classes-and-structs/anonymous-types.md).

I tipi valore comuni non possono avere un valore [null](../../language-reference/keywords/null.md). È tuttavia possibile creare tipi valore nullable aggiungendo `?` dopo il tipo. Ad esempio, `int?` è un tipo `int` che può avere anche il valore [null](../../language-reference/keywords/null.md). I tipi di valore nullable sono istanze del tipo di struct generico <xref:System.Nullable%601?displayProperty=nameWithType>. I tipi di valore nullable sono particolarmente utili quando si passano dati da e verso database in cui i valori numerici potrebbero essere null. Per altre informazioni, vedere [tipi di valore Nullable](../../language-reference/builtin-types/nullable-value-types.md).

## <a name="related-sections"></a>Sezioni correlate

Per altre informazioni, vedere gli argomenti seguenti:

- [Cast e conversioni di tipi](./casting-and-type-conversions.md)

- [Boxing e unboxing](./boxing-and-unboxing.md)

- [Uso del tipo dinamico](./using-type-dynamic.md)

- [Tipi di valore](../../language-reference/builtin-types/value-types.md)

- [Tipi di riferimento](../../language-reference/keywords/reference-types.md)

- [Classi e struct](../classes-and-structs/index.md)

- [Tipi anonimi](../classes-and-structs/anonymous-types.md)

- [Generics](../generics/index.md)

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../language-reference/index.md)
- [Guida per programmatori C#](../index.md)
- [Conversione dei tipi di dati XML](../../../standard/data/xml/conversion-of-xml-data-types.md)
- [Tipi integrali](../../language-reference/builtin-types/integral-numeric-types.md)
