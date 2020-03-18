---
title: Polimorfismo - Guida per programmatori C#
ms.date: 02/08/2020
helpviewer_keywords:
- C# language, polymorphism
- polymorphism [C#]
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
ms.openlocfilehash: 58980bd0d70d8a778cdb208f56d31ee8465871a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170169"
---
# <a name="polymorphism-c-programming-guide"></a>Polimorfismo (Guida per programmatori C#)

Il polimorfismo è spesso definito il terzo pilastro della programmazione orientata a oggetti, dopo l'incapsulamento e l'ereditarietà. Polimorfismo è una parola che deriva dal greco e significa "multiforme". Il polimorfismo presenta due aspetti distinti:
  
- In fase di esecuzione, oggetti di una classe derivata possono essere trattati come oggetti di una classe base in posizioni quali parametri del metodo e raccolte o matrici. Quando si verifica questo polimorfismo, il tipo dichiarato dell'oggetto non è più identico al tipo in fase di esecuzione.
- Le classi di base possono definire e implementare *metodi* [virtuali](../../language-reference/keywords/virtual.md) e le classi derivate possono [eseguirne l'override,](../../language-reference/keywords/override.md) il che significa che forniscono la propria definizione e implementazione. Durante la fase di esecuzione, quando il codice client chiama il metodo, CLR cerca il tipo in fase di esecuzione dell'oggetto e richiama quell'override del metodo virtuale. Nel codice sorgente è possibile chiamare un metodo su una classe base e causare la versione del metodo di una classe derivata.

I metodi virtuali consentono di usare gruppi di oggetti correlati in modo uniforme. Si supponga ad esempio di avere un'applicazione di disegno che consenta a un utente di creare vari tipi di forme in un'area di disegno. In fase di compilazione non è possibile sapere i tipi specifici di forme che l'utente creerà. L'applicazione deve tuttavia tenere traccia di tutti i vari tipi di forme create e deve aggiornarli in risposta alle azioni del mouse dell'utente. È possibile usare il polimorfismo per risolvere questo problema in due passaggi di base:

1. Creare una gerarchia di classi nella quale ogni classe della forma specifica deriva da una classe base comune.
1. Usare un metodo virtuale per richiamare il metodo adatto su qualsiasi classe derivata tramite una sola chiamata al metodo della classe base.

Prima di tutto, creare una classe base denominata `Shape` e delle classi derivate quali `Rectangle`, `Circle` e `Triangle`. Definire nella classe `Shape` un metodo virtuale denominato `Draw` ed eseguirne l'override in ogni classe derivata per disegnare la particolare forma che la classe rappresenta. Creare `List<Shape>` un oggetto `Circle`e `Triangle`aggiungervi un oggetto , e `Rectangle` ad esso.

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#PolymorphismOverview)]

Per aggiornare l'area di disegno, usare un ciclo [foreach](../../language-reference/keywords/foreach-in.md) per scorrere l'elenco e chiamare il metodo `Draw` su ogni oggetto `Shape` nell'elenco. Anche se ogni oggetto nell'elenco `Shape`dispone di un tipo dichiarato di , è il tipo in fase di esecuzione (la versione sottoposta a override del metodo in ogni classe derivata) che verrà richiamato.

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UsePolymorphism)]

In C# ogni tipo è polimorfico perché tutti i tipi, incluso i tipi definiti dall'utente, ereditano da <xref:System.Object>.  

## <a name="polymorphism-overview"></a>Panoramica del polimorfismo

### <a name="virtual-members"></a>Membri virtuali

Quando una classe derivata eredita da una classe base, ottiene tutti i metodi, i campi, le proprietà e gli eventi della classe base. La finestra di progettazione della classe derivata può scegliere diverse per il comportamento dei metodi virtuali:The designer of the derived class can different choices for the behavior of virtual methods:

- La classe derivata può eseguire l'override dei membri virtuali nella classe base, definendo un nuovo comportamento.
- La classe derivata eredita il metodo della classe base più vicino senza eseguirne l'override, preservando il comportamento esistente ma consentendo alle altre classi derivate di eseguire l'override del metodo.
- La classe derivata può definire una nuova implementazione non virtuale dei membri che nascondono le implementazioni della classe base.

Una classe derivata può eseguire l'override di un membro della classe base solo se quest'ultimo è dichiarato come [virtuale](../../language-reference/keywords/virtual.md) o [astratto](../../language-reference/keywords/abstract.md). Il membro derivato deve usare la parola chiave [override](../../language-reference/keywords/override.md) per indicare esplicitamente che il metodo deve partecipare alla chiamata virtuale. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[Virtual overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#VirtualMethods)]

I campi non possono essere virtuali; solo metodi, proprietà, eventi e indicizzatori possono essere virtuali. Quando una classe derivata esegue l'override di un membro virtuale, quest'ultimo viene chiamato anche nel caso in cui si acceda a un'istanza di tale classe come istanza della classe base. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[Virtual overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#VirtualMethods)]

Metodi virtuali e proprietà consentono alle classi derivate di estendere una classe base senza dover usare l'implementazione della classe base di un metodo. Per altre informazioni, vedere [Controllo delle versioni con le parole chiave Override e New](./versioning-with-the-override-and-new-keywords.md). Un'interfaccia fornisce un'altra modalità per definire un metodo o un insieme di metodi la cui implementazione è lasciata alle classi derivate. Per ulteriori informazioni, vedi [Interfacce](../interfaces/index.md).

### <a name="hide-base-class-members-with-new-members"></a>Nascondere i membri della classe base con nuovi membri

Se si desidera che la classe derivata abbia un membro con lo stesso nome di un membro in una classe base, è possibile utilizzare la parola chiave [new](../../language-reference/keywords/new-modifier.md) per nascondere il membro della classe base. La parola chiave `new` viene inserita prima del tipo restituito di un membro di classe che viene sostituito. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[New method overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#NewMethods)]

È possibile accedere ai membri della classe base nascosti dal codice client eseguendo il cast dell'istanza della classe derivata in un'istanza della classe base. Ad esempio:

[!code-csharp[New method overview usage](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UseNewMethods)]

### <a name="prevent-derived-classes-from-overriding-virtual-members"></a>Impedire alle classi derivate di eseguire l'override dei membri virtuali  

I membri virtuali rimangono virtuali, indipendentemente dal numero di classi dichiarate tra il membro virtuale e la classe che lo ha originariamente dichiarato. Se `A` la classe dichiara un `B` membro virtuale `A`e `C` la classe `B`deriva `C` da , e la classe deriva da , `B` la classe eredita il membro virtuale e può eseguirne l'override, indipendentemente dal fatto che la classe abbia dichiarato un override per tale membro. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[Basic hierarchy](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#FirstHierarchy)]

Una classe derivata può interrompere l'ereditarietà virtuale dichiarando un override come [sealed](../../language-reference/keywords/sealed.md). L'interruzione dell'ereditarietà richiede l'inserimento della `sealed` parola chiave prima della `override` parola chiave nella dichiarazione del membro della classe. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[A sealed overridden member](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#SealedOverride)]

Nell'esempio precedente, `DoWork` il metodo non è più `C`virtuale per qualsiasi classe derivata da . È ancora virtuale per `C`le istanze di , `B` anche `A`se ne viene esegetta il cast nel tipo o nel tipo . I metodi sealed possono essere sostituiti dalle classi derivate usando la parola chiave , come illustrato nell'esempio seguente:Sealed methods can be replaced by derived classes by using the `new` keyword, as the following example shows:

[!code-csharp[New method declaration](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#NewDeclaration)]

In questo caso, `DoWork` se `D` viene chiamato `D`utilizzando una `DoWork` variabile di tipo , viene chiamato il nuovo. Se una variabile `C` `B`di `A` tipo , , o `D`viene utilizzata `DoWork` per accedere a un'istanza di , `DoWork` una `C`chiamata a seguirà le regole dell'ereditarietà virtuale, instradando tali chiamate all'implementazione di sulla classe .

### <a name="access-base-class-virtual-members-from-derived-classes"></a>Accedere ai membri virtuali della classe base dalle classi derivateAccess base class virtual members from derived classes

Una classe derivata che ha sostituito un metodo o una proprietà, o ne ha eseguito l'override, può ancora accedere al metodo o alla proprietà sulla classe base usando la parola chiave `base`. Nel codice seguente ne viene illustrato un esempio:

```csharp
public class Base
{
    public virtual void DoWork() {/*...*/ }
}
public class Derived : Base
{
    public override void DoWork()
    {
        //Perform Derived's work here
        //...
        // Call DoWork on base class
        base.DoWork();
    }
}
```

Per altre informazioni, vedere [base](../../language-reference/keywords/base.md).

> [!NOTE]
> Nell'implementazione dei membri virtuali è consigliabile l'uso della parola chiave `base` per le chiamate all'implementazione della classe base di tali membri. In questo modo, nella classe derivata sarà possibile definire la sola implementazione del comportamento specifico per tale classe. Se l'implementazione della classe base non viene chiamata, spetterà alla classe derivata rendere il proprio comportamento compatibile con quello della classe base.

## <a name="in-this-section"></a>Contenuto della sezione

- [Controllo delle versioni con le parole chiave Override e New](./versioning-with-the-override-and-new-keywords.md)
- [Sapere quando utilizzare le parole chiave Override e New](./knowing-when-to-use-override-and-new-keywords.md)
- [Come eseguire l'override del metodo ToString](./how-to-override-the-tostring-method.md)

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Ereditarietà](./inheritance.md)
- [Classi e membri delle classi astratte e sealed](./abstract-and-sealed-classes-and-class-members.md)
- [Metodi](./methods.md)
- [Events](../events/index.md)
- [Proprietà](./properties.md)
- [Indicizzatori](../indexers/index.md)
- [Tipi](../types/index.md)
