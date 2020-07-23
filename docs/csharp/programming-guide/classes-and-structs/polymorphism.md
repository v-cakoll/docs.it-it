---
title: Polimorfismo - Guida per programmatori C#
description: Informazioni sul polimorfismo, un concetto chiave nei linguaggi di programmazione orientati a oggetti come C#, che descrive la relazione tra le classi base e derivate.
ms.date: 02/08/2020
helpviewer_keywords:
- C# language, polymorphism
- polymorphism [C#]
ms.assetid: 086af969-29a5-4ce8-a993-0b7d53839dab
ms.openlocfilehash: 59b5f5d2d5a8f274845607aeca370c316670bd68
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925449"
---
# <a name="polymorphism-c-programming-guide"></a>Polimorfismo (Guida per programmatori C#)

Il polimorfismo è spesso definito il terzo pilastro della programmazione orientata a oggetti, dopo l'incapsulamento e l'ereditarietà. Polimorfismo è una parola che deriva dal greco e significa "multiforme". Il polimorfismo presenta due aspetti distinti:
  
- In fase di esecuzione, oggetti di una classe derivata possono essere trattati come oggetti di una classe base in posizioni quali parametri del metodo e raccolte o matrici. Quando si verifica questo polimorfismo, il tipo dichiarato dell'oggetto non è più identico al tipo in fase di esecuzione.
- Le classi base possono definire e implementare *Metodi* [virtuali](../../language-reference/keywords/virtual.md) e le classi derivate possono [eseguirne l'override](../../language-reference/keywords/override.md) , il che significa che forniscono la definizione e l'implementazione. Durante la fase di esecuzione, quando il codice client chiama il metodo, CLR cerca il tipo in fase di esecuzione dell'oggetto e richiama quell'override del metodo virtuale. Nel codice sorgente è possibile chiamare un metodo su una classe di base e causare l'esecuzione di una versione della classe derivata del metodo.

I metodi virtuali consentono di usare gruppi di oggetti correlati in modo uniforme. Si supponga ad esempio di avere un'applicazione di disegno che consenta a un utente di creare vari tipi di forme in un'area di disegno. In fase di compilazione non è possibile sapere i tipi specifici di forme che l'utente creerà. L'applicazione deve tuttavia tenere traccia di tutti i vari tipi di forme create e deve aggiornarli in risposta alle azioni del mouse dell'utente. È possibile usare il polimorfismo per risolvere questo problema in due passaggi di base:

1. Creare una gerarchia di classi nella quale ogni classe della forma specifica deriva da una classe base comune.
1. Usare un metodo virtuale per richiamare il metodo adatto su qualsiasi classe derivata tramite una sola chiamata al metodo della classe base.

Prima di tutto, creare una classe base denominata `Shape` e delle classi derivate quali `Rectangle`, `Circle` e `Triangle`. Definire nella classe `Shape` un metodo virtuale denominato `Draw` ed eseguirne l'override in ogni classe derivata per disegnare la particolare forma che la classe rappresenta. Creare un `List<Shape>` oggetto e aggiungervi un oggetto `Circle` , `Triangle` e `Rectangle` .

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#PolymorphismOverview)]

Per aggiornare l'area di disegno, usare un ciclo [foreach](../../language-reference/keywords/foreach-in.md) per scorrere l'elenco e chiamare il metodo `Draw` su ogni oggetto `Shape` nell'elenco. Anche se ogni oggetto nell'elenco ha un tipo dichiarato di `Shape` , è il tipo in fase di esecuzione (la versione sottoposta a override del metodo in ogni classe derivata) che verrà richiamato.

[!code-csharp[Polymorphism overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UsePolymorphism)]

In C# ogni tipo è polimorfico perché tutti i tipi, incluso i tipi definiti dall'utente, ereditano da <xref:System.Object>.  

## <a name="polymorphism-overview"></a>Cenni preliminari sul polimorfismo

### <a name="virtual-members"></a>Membri virtuali

Quando una classe derivata eredita da una classe base, ottiene tutti i metodi, i campi, le proprietà e gli eventi della classe di base. La finestra di progettazione della classe derivata ha scelte diverse per il comportamento dei metodi virtuali:

- La classe derivata può eseguire l'override dei membri virtuali della classe di base, definendo un nuovo comportamento.
- La classe derivata eredita il metodo della classe base più vicino senza eseguirne l'override, mantenendo il comportamento esistente ma abilitando ulteriori classi derivate per eseguire l'override del metodo.
- La classe derivata può definire una nuova implementazione non virtuale dei membri che nascondono le implementazioni della classe di base.

Una classe derivata può eseguire l'override di un membro della classe base solo se quest'ultimo è dichiarato come [virtuale](../../language-reference/keywords/virtual.md) o [astratto](../../language-reference/keywords/abstract.md). Il membro derivato deve usare la parola chiave [override](../../language-reference/keywords/override.md) per indicare esplicitamente che il metodo deve partecipare alla chiamata virtuale. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[Virtual overview](~/samples/snippets/csharp/objectoriented/Inheritance.cs#VirtualMethods)]

I campi non possono essere virtuali. solo i metodi, le proprietà, gli eventi e gli indicizzatori possono essere virtuali. Quando una classe derivata esegue l'override di un membro virtuale, quest'ultimo viene chiamato anche nel caso in cui si acceda a un'istanza di tale classe come istanza della classe base. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[Virtual overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#SnippetTestVirtualMethods)]

Metodi virtuali e proprietà consentono alle classi derivate di estendere una classe base senza dover usare l'implementazione della classe base di un metodo. Per altre informazioni, vedere [Controllo delle versioni con le parole chiave Override e New](./versioning-with-the-override-and-new-keywords.md). Un'interfaccia fornisce un'altra modalità per definire un metodo o un insieme di metodi la cui implementazione è lasciata alle classi derivate. Per ulteriori informazioni, vedi [Interfacce](../interfaces/index.md).

### <a name="hide-base-class-members-with-new-members"></a>Nascondi membri della classe di base con nuovi membri

Se si vuole che la classe derivata disponga di un membro con lo stesso nome di un membro in una classe di base, è possibile usare la parola chiave [New](../../language-reference/keywords/new-modifier.md) per nascondere il membro della classe base. La parola chiave `new` viene inserita prima del tipo restituito di un membro di classe che viene sostituito. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[New method overview example](~/samples/snippets/csharp/objectoriented/Inheritance.cs#NewMethods)]

È possibile accedere ai membri nascosti della classe base dal codice client eseguendo il cast dell'istanza della classe derivata a un'istanza della classe di base. Ad esempio:

[!code-csharp[New method overview usage](~/samples/snippets/csharp/objectoriented/Inheritance.cs#UseNewMethods)]

### <a name="prevent-derived-classes-from-overriding-virtual-members"></a>Impedire alle classi derivate di eseguire l'override dei membri virtuali  

I membri virtuali rimangono virtuali, indipendentemente dal numero di classi dichiarate tra il membro virtuale e la classe che l'ha originariamente dichiarata. Se la classe `A` dichiara un membro virtuale e la classe `B` deriva da `A` , e la classe `C` deriva da `B` , la classe `C` eredita il membro virtuale ed è possibile eseguirne l'override, indipendentemente dal fatto che la classe abbia `B` dichiarato una sostituzione per quel membro. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[Basic hierarchy](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#FirstHierarchy)]

Una classe derivata può interrompere l'ereditarietà virtuale dichiarando un override come [sealed](../../language-reference/keywords/sealed.md). Per arrestare l'ereditarietà è necessario inserire la `sealed` parola chiave prima della `override` parola chiave nella dichiarazione del membro della classe. Nel codice seguente ne viene illustrato un esempio:

[!code-csharp[A sealed overridden member](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#SealedOverride)]

Nell'esempio precedente, il metodo `DoWork` non è più virtuale per le classi derivate da `C` . È ancora virtuale per le istanze di `C` , anche se ne viene eseguito il cast al tipo `B` o al tipo `A` . I metodi sealed possono essere sostituiti da classi derivate tramite la `new` parola chiave, come illustrato nell'esempio seguente:

[!code-csharp[New method declaration](~/samples/snippets/csharp/objectoriented/Hierarchy.cs#NewDeclaration)]

In questo caso, se `DoWork` viene chiamato su `D` utilizzando una variabile di tipo `D` , `DoWork` viene chiamato il nuovo. Se una variabile di tipo `C` , `B` o `A` viene utilizzata per accedere a un'istanza di `D` , una chiamata a `DoWork` seguirà le regole dell'ereditarietà virtuale, indirizzando tali chiamate all'implementazione di `DoWork` nella classe `C` .

### <a name="access-base-class-virtual-members-from-derived-classes"></a>Accedere ai membri virtuali della classe di base dalle classi derivate

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
