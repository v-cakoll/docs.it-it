---
title: Ereditarietà - Guida per programmatori C#
description: L'ereditarietà in C# consente di creare nuove classi che riutilizzano, estendono e modificano il comportamento definito in altre classi.
ms.date: 02/07/2020
helpviewer_keywords:
- abstract methods [C#]
- abstract classes [C#]
- inheritance [C#]
- derived classes [C#]
- virtual methods [C#]
- C# language, inheritance
ms.assetid: 81d64ee4-50f9-4d6c-a8dc-257c348d2eea
ms.openlocfilehash: 6b94f58801af188655474f9c7de76b79381e721d
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864255"
---
# <a name="inheritance-c-programming-guide"></a>Ereditarietà (Guida per programmatori C#)

L'ereditarietà, insieme all'incapsulamento e al polimorfismo, rappresenta una delle tre principali caratteristiche (o pilastri) della programmazione orientata a oggetti. L'ereditarietà consente di creare nuove classi che riutilizzano, estendono e modificano il comportamento definito in altre classi. La classe i cui membri vengono ereditati è denominata *classe di base*, mentre la classe che eredita tali membri è denominata *classe derivata*. Una classe derivata può avere una sola classe di base diretta. L'ereditarietà, tuttavia, è transitiva. Se `ClassC` è derivato da `ClassB` ed `ClassB` è derivato da `ClassA` , `ClassC` eredita i membri dichiarati in `ClassB` e `ClassA` .

> [!NOTE]
> Gli struct non supportano l'ereditarietà, mentre possono implementare interfacce. Per ulteriori informazioni, vedi [Interfacce](../interfaces/index.md).

Concettualmente, una classe derivata rappresenta una specializzazione della classe di base. Ad esempio, avendo una classe di base `Animal`, è possibile definire una classe derivata denominata `Mammal` e un'altra classe derivata denominata `Reptile`. Un oggetto `Mammal` è anche un oggetto `Animal` e un oggetto `Reptile` è anche un `Animal`, ma ogni classe derivata rappresenta una diversa specializzazione della classe di base.

Le dichiarazioni di interfaccia possono definire un'implementazione predefinita per i relativi membri. Queste implementazioni vengono ereditate dalle interfacce derivate e dalle classi che implementano tali interfacce. Per ulteriori informazioni sui metodi di interfaccia predefiniti, vedere l'articolo sulle [interfacce](../../language-reference/keywords/interface.md) nella sezione riferimento al linguaggio.

Quando si definisce una classe derivandola da un'altra classe, la classe derivata acquista implicitamente tutti i membri della classe di base, con l'eccezione dei costruttori e dei finalizzatori. La classe derivata riutilizza il codice nella classe di base senza doverlo reimplementare. È possibile aggiungere altri membri nella classe derivata. La classe derivata estende la funzionalità della classe di base.

La figura riportata di seguito illustra una classe `WorkItem` che rappresenta un elemento di lavoro in un qualche processo aziendale. Come per tutte le classi, è derivata da <xref:System.Object?displayProperty=nameWithType> ed eredita tutti i metodi di tale classe. `WorkItem` aggiunge cinque propri membri, Questi membri includono un costruttore, perché i costruttori non vengono ereditati. La classe `ChangeRequest` eredita da `WorkItem` e rappresenta un particolare tipo di elemento di lavoro. `ChangeRequest` aggiunge altri due membri ai membri che eredita da `WorkItem` e da <xref:System.Object>. Deve aggiungere il proprio costruttore e aggiunge anche `originalItemID`. La proprietà `originalItemID` consente l'associazione dell'istanza di `ChangeRequest` all'oggetto `WorkItem` originale a cui si applica la richiesta di modifica.

![Diagramma che illustra l'ereditarietà delle classi](./media/inheritance/class-inheritance-diagram.png)

Nell'esempio seguente viene illustrato come le relazioni tra le classi mostrate nella precedente illustrazione vengono espresse in C#. Nell'esempio viene descritto anche come `WorkItem` esegue l'override del metodo virtuale <xref:System.Object.ToString%2A?displayProperty=nameWithType> e come la classe `ChangeRequest` eredita l'implementazione del metodo propria della classe `WorkItem`. Il primo blocco definisce le classi:

[!code-csharp[DefineClasses](~/samples/snippets/csharp/objectoriented/inheritance.cs#Classes)]

Questo blocco successivo Mostra come usare le classi base e derivate:

[!code-csharp[UseClasses](~/samples/snippets/csharp/objectoriented/inheritance.cs#UseClasses)]

## <a name="abstract-and-virtual-methods"></a>Metodi astratti e virtuali

Quando una classe di base dichiara un metodo come [`virtual`](../../language-reference/keywords/virtual.md) , una classe derivata può usare [`override`](../../language-reference/keywords/override.md) il metodo con la propria implementazione. Se una classe di base dichiara un membro come [`abstract`](../../language-reference/keywords/abstract.md) , è necessario eseguire l'override di tale metodo in una classe non astratta che eredita direttamente da tale classe. Quando una classe derivata è essa stessa astratta, eredita i membri astratti senza implementarli. I membri astratti e virtuali costituiscono la base del polimorfismo, che rappresenta la seconda principale caratteristica della programmazione orientata a oggetti. Per altre informazioni, vedere [Polimorfismo](./polymorphism.md).

## <a name="abstract-base-classes"></a>Classi base astratte

Se si vuole evitare la generazione di istanze dirette di una classe, è possibile dichiarare una classe come [abstract](../../language-reference/keywords/abstract.md) usando l'operatore [new](../../language-reference/operators/new-operator.md). Una classe astratta può essere utilizzata solo se viene derivata una nuova classe. Una classe astratta può contenere una o più firme di metodi, a loro volta dichiarate come astratte. Tali firme specificano i parametri e il valore restituito, ma non definiscono alcuna implementazione (corpo del metodo). Una classe astratta non deve contenere membri astratti; Tuttavia, se una classe contiene un membro astratto, la classe deve essere dichiarata come astratta. Le classi derivate che non sono astratte devono fornire l'implementazione per tutti i metodi astratti da una classe base astratta. Per altre informazioni, vedere [classi e membri delle classi astratte e sealed](abstract-and-sealed-classes-and-class-members.md).

## <a name="interfaces"></a>Interfacce

Un' *interfaccia* è un tipo riferimento che definisce un set di membri. Tutte le classi e gli struct che implementano tale interfaccia devono implementare tale set di membri. Un'interfaccia può definire un'implementazione predefinita per uno o tutti questi membri. Una classe può implementare più interfacce, anche se può essere derivata solo da una singola classe di base diretta.

Le interfacce vengono usate per definire funzionalità specifiche per le classi che non hanno necessariamente una relazione "is a". Ad esempio, l' <xref:System.IEquatable%601?displayProperty=nameWithType> interfaccia può essere implementata da qualsiasi classe o struct per determinare se due oggetti del tipo sono equivalenti, ma il tipo definisce l'equivalenza. <xref:System.IEquatable%601>non implica lo stesso tipo di relazione "is a" esistente tra una classe di base e una classe derivata, ad esempio un oggetto `Mammal` `Animal` . Per ulteriori informazioni, vedi [Interfacce](../interfaces/index.md).

## <a name="preventing-further-derivation"></a>Impedisci ulteriore derivazione  

Una classe può impedire che altre classi ereditino da esso o da uno dei relativi membri, dichiarando se stesso o il membro come [`sealed`](../../language-reference/keywords/sealed.md) . Per altre informazioni, vedere [classi e membri delle classi astratte e sealed](./abstract-and-sealed-classes-and-class-members.md).

## <a name="derived-class-hiding-of-base-class-members"></a>Classe derivata che nasconde i membri della classe base  

Una classe derivata può nascondere i membri di una classe di base dichiarando dei membri con lo stesso nome e la stessa firma. Il [`new`](../../language-reference/keywords/new-modifier.md) modificatore può essere usato per indicare in modo esplicito che il membro non è destinato a essere un override del membro di base. L'uso di [`new`](../../language-reference/keywords/new-modifier.md) non è obbligatorio, ma viene generato un avviso del compilatore se [`new`](../../language-reference/keywords/new-modifier.md) non viene usato. Per altre informazioni, vedere [Controllo delle versioni con le parole chiave Override e New](./versioning-with-the-override-and-new-keywords.md) e [Sapere quando usare le parole chiave Override e New](./knowing-when-to-use-override-and-new-keywords.md).

## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [class](../../language-reference/keywords/class.md)
