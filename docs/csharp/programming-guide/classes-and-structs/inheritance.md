---
title: Ereditarietà - Guida per programmatori C#
ms.date: 02/07/2020
helpviewer_keywords:
- abstract methods [C#]
- abstract classes [C#]
- inheritance [C#]
- derived classes [C#]
- virtual methods [C#]
- C# language, inheritance
ms.assetid: 81d64ee4-50f9-4d6c-a8dc-257c348d2eea
ms.openlocfilehash: 448b1695a4afc50f4afa20383e5fda280b9f12e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626659"
---
# <a name="inheritance-c-programming-guide"></a>Ereditarietà (Guida per programmatori C#)

L'ereditarietà, insieme all'incapsulamento e al polimorfismo, rappresenta una delle tre principali caratteristiche (o pilastri) della programmazione orientata a oggetti. L'ereditarietà consente di creare nuove classi che riutilizzano, estendono e modificano il comportamento definito in altre classi. La classe i cui membri vengono ereditati è denominata *classe di base*, mentre la classe che eredita tali membri è denominata *classe derivata*. Una classe derivata può avere una sola classe di base diretta. L'ereditarietà, tuttavia, è transitiva. Se `ClassC` è `ClassB`derivato `ClassB` da `ClassA`, `ClassC` ed è derivato da , eredita i membri dichiarati in `ClassB` e `ClassA`.

> [!NOTE]
> Gli struct non supportano l'ereditarietà, mentre possono implementare interfacce. Per ulteriori informazioni, vedi [Interfacce](../interfaces/index.md).

Concettualmente, una classe derivata rappresenta una specializzazione della classe di base. Ad esempio, avendo una classe di base `Animal`, è possibile definire una classe derivata denominata `Mammal` e un'altra classe derivata denominata `Reptile`. Un oggetto `Mammal` è anche un oggetto `Animal` e un oggetto `Reptile` è anche un `Animal`, ma ogni classe derivata rappresenta una diversa specializzazione della classe di base.

Le dichiarazioni di interfaccia possono definire un'implementazione predefinita per i relativi membri. Queste implementazioni vengono ereditate dalle interfacce derivate e dalle classi che implementano tali interfacce. Per altre informazioni sui metodi di interfaccia predefiniti, vedere l'articolo sulle [interfacce](../../language-reference/keywords/interface.md) nella sezione di riferimento del linguaggio.

Quando si definisce una classe derivandola da un'altra classe, la classe derivata acquista implicitamente tutti i membri della classe di base, con l'eccezione dei costruttori e dei finalizzatori. La classe derivata riutilizza il codice nella classe base senza doverlo reimplementare. È possibile aggiungere più membri nella classe derivata. La classe derivata estende la funzionalità della classe base.

La figura riportata di seguito illustra una classe `WorkItem` che rappresenta un elemento di lavoro in un qualche processo aziendale. Come per tutte le classi, è derivata da <xref:System.Object?displayProperty=nameWithType> ed eredita tutti i metodi di tale classe. `WorkItem` aggiunge cinque propri membri, Questi membri includono un costruttore, perché i costruttori non vengono ereditati. La classe `ChangeRequest` eredita da `WorkItem` e rappresenta un particolare tipo di elemento di lavoro. `ChangeRequest` aggiunge altri due membri ai membri che eredita da `WorkItem` e da <xref:System.Object>. Deve aggiungere il proprio costruttore e aggiunge anche `originalItemID`. La proprietà `originalItemID` consente l'associazione dell'istanza di `ChangeRequest` all'oggetto `WorkItem` originale a cui si applica la richiesta di modifica.

![Diagramma che illustra l'ereditarietà delle classi](./media/inheritance/class-inheritance-diagram.png)

Nell'esempio seguente viene illustrato come le relazioni tra le classi mostrate nella precedente illustrazione vengono espresse in C#. Nell'esempio viene descritto anche come `WorkItem` esegue l'override del metodo virtuale <xref:System.Object.ToString%2A?displayProperty=nameWithType> e come la classe `ChangeRequest` eredita l'implementazione del metodo propria della classe `WorkItem`. Il primo blocco definisce le classi:

[!code-csharp[DefineClasses](~/samples/snippets/csharp/objectoriented/inheritance.cs#Classes)]

Questo blocco successivo viene illustrato come utilizzare le classi base e derivate:This next block shows how to use the base and derived classes:

[!code-csharp[UseClasses](~/samples/snippets/csharp/objectoriented/inheritance.cs#UseClasses)]

## <a name="abstract-and-virtual-methods"></a>Metodi astratti e virtuali

Quando una classe base dichiara [`virtual`](../../language-reference/keywords/virtual.md)un metodo [`override`](../../language-reference/keywords/override.md) come , una classe derivata può utilizzare il metodo con la propria implementazione. Se una classe base dichiara [`abstract`](../../language-reference/keywords/abstract.md)un membro come , tale metodo deve essere sottoposto a override in qualsiasi classe non astratta che eredita direttamente da tale classe. Quando una classe derivata è essa stessa astratta, eredita i membri astratti senza implementarli. I membri astratti e virtuali costituiscono la base del polimorfismo, che rappresenta la seconda principale caratteristica della programmazione orientata a oggetti. Per altre informazioni, vedere [Polimorfismo](./polymorphism.md).

## <a name="abstract-base-classes"></a>Classi base astratte

Se si vuole evitare la generazione di istanze dirette di una classe, è possibile dichiarare una classe come [abstract](../../language-reference/keywords/abstract.md) usando l'operatore [new](../../language-reference/operators/new-operator.md). Una classe astratta può essere utilizzata solo se da essa deriva una nuova classe. Una classe astratta può contenere una o più firme di metodi, a loro volta dichiarate come astratte. Tali firme specificano i parametri e il valore restituito, ma non definiscono alcuna implementazione (corpo del metodo). Una classe astratta non deve contenere membri astratti. Tuttavia, se una classe contiene un membro astratto, la classe stessa deve essere dichiarata come astratta. Le classi derivate che non sono astratte devono fornire l'implementazione per tutti i metodi astratti da una classe base astratta. Per ulteriori informazioni, vedere [Classi astratte e sealed e Membri di classe](abstract-and-sealed-classes-and-class-members.md).

## <a name="interfaces"></a>Interfacce

*Un'interfaccia* è un tipo di riferimento che definisce un set di membri. Tutte le classi e gli struct che implementano tale interfaccia devono implementare tale set di membri. Un'interfaccia può definire un'implementazione predefinita per uno o tutti questi membri. Una classe può implementare più interfacce, anche se può essere derivata solo da una singola classe di base diretta.

Le interfacce vengono utilizzate per definire funzionalità specifiche per le classi che non hanno necessariamente una relazione "è un". Ad esempio, <xref:System.IEquatable%601?displayProperty=nameWithType> l'interfaccia può essere implementata da qualsiasi classe o struct per determinare se due oggetti del tipo sono equivalenti (tuttavia il tipo definisce l'equivalenza). <xref:System.IEquatable%601>non implica lo stesso tipo di relazione "è un" esistente tra una classe base `Mammal` e `Animal`una classe derivata (ad esempio, a è un ). Per ulteriori informazioni, vedi [Interfacce](../interfaces/index.md).

## <a name="preventing-further-derivation"></a>Prevenire un'ulteriore derivazione  

Una classe può impedire ad altre classi di ereditare da essa o da [`sealed`](../../language-reference/keywords/sealed.md)uno dei relativi membri dichiarando se stessa o il membro come . Per ulteriori informazioni, vedere [Classi astratte e sealed e Membri di classe](./abstract-and-sealed-classes-and-class-members.md).

## <a name="derived-class-hiding-of-base-class-members"></a>Classe derivata nascosta dai membri della classe base  

Una classe derivata può nascondere i membri di una classe di base dichiarando dei membri con lo stesso nome e la stessa firma. Il [`new`](../../language-reference/keywords/new-modifier.md) modificatore può essere utilizzato per indicare in modo esplicito che il membro non deve essere un override del membro di base. L'uso [`new`](../../language-reference/keywords/new-modifier.md) di non è obbligatorio, ma verrà [`new`](../../language-reference/keywords/new-modifier.md) generato un avviso del compilatore se non viene utilizzato. Per altre informazioni, vedere [Controllo delle versioni con le parole chiave Override e New](./versioning-with-the-override-and-new-keywords.md) e [Sapere quando usare le parole chiave Override e New](./knowing-when-to-use-override-and-new-keywords.md).

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Classe](../../language-reference/keywords/class.md)
