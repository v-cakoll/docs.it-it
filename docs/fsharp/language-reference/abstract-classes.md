---
title: Classi astratte
description: Informazioni sulle F# classi astratte, che lasciano alcuni o tutti i membri non implementati e rappresentano funzionalità comuni di un set diversificato di tipi di oggetti.
ms.date: 05/16/2016
ms.openlocfilehash: a6bbfc23b858d5f3833f3f52b6dca46753080f03
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629674"
---
# <a name="abstract-classes"></a>Classi astratte

*Le classi astratte* sono classi che lasciano inimplementati alcuni o tutti i membri, in modo che le implementazioni possano essere fornite dalle classi derivate.

## <a name="syntax"></a>Sintassi

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a>Note

Nella programmazione orientata a oggetti, una classe astratta viene utilizzata come classe di base di una gerarchia e rappresenta la funzionalità comune di un diverso set di tipi di oggetti. Come suggerisce il nome "abstract", le classi astratte spesso non corrispondono direttamente a entità concrete nel dominio del problema. Tuttavia, rappresentano il numero di entità concrete diverse in comune.

Le classi astratte devono `AbstractClass` avere l'attributo. Possono avere membri implementati e non implementati. L'utilizzo del termine *abstract* quando viene applicato a una classe è uguale a quello di altri linguaggi .NET; Tuttavia, l'uso del termine *abstract* quando viene applicato ai metodi e alle proprietà è leggermente diverso in F# dal suo uso in altri linguaggi .NET. In F#, quando un metodo è contrassegnato con la `abstract` parola chiave, questo indica che un membro dispone di una voce, nota come *slot di invio virtuale*, nella tabella interna delle funzioni virtuali per quel tipo. In altre parole, il metodo è virtuale, anche se `virtual` la parola chiave non viene usata F# nel linguaggio. La parola `abstract` chiave viene usata nei metodi virtuali indipendentemente dal fatto che il metodo venga implementato. La dichiarazione di uno slot di invio virtuale è separata dalla definizione di un metodo per lo slot di distribuzione. Pertanto, l' F# equivalente di una dichiarazione di metodo virtuale e di una definizione in un altro linguaggio .NET è costituito da una combinazione di una dichiarazione di metodo astratto e `default` di una definizione `override` separata, con la parola chiave o la parola chiave. Per ulteriori informazioni ed esempi, vedere [Metodi](./members/methods.md).

Una classe viene considerata astratta solo se sono presenti metodi astratti dichiarati ma non definiti. Pertanto, le classi con metodi astratti non sono necessariamente classi astratte. A meno che una classe non disponga di metodi astratti non definiti, non usare l'attributo **AbstractClass** .

Nella sintassi precedente, il *modificatore* di accessibilità `public`può `private` essere `internal`, o. Per altre informazioni, vedere [Controllo di accesso](access-control.md).

Come per gli altri tipi, le classi astratte possono avere una classe di base e una o più interfacce di base. Ogni classe o interfaccia di base viene visualizzata in una riga distinta `inherit` insieme alla parola chiave.

La definizione del tipo di una classe astratta può contenere membri completamente definiti, ma può contenere anche membri astratti. La sintassi per i membri astratti viene mostrata separatamente nella sintassi precedente. In questa sintassi, la *firma del tipo* di un membro è un elenco che contiene i tipi di parametro nell'ordine e i tipi restituiti, `->` separati dai token e/ `*` o dai token come appropriato per i parametri sottoposti a currying e con tupla. La sintassi per le firme dei tipi di membro abstract è identica a quella utilizzata nei file di firma e mostrata da IntelliSense nell'editor di Visual Studio Code.

Nel codice seguente viene illustrata una forma di classe astratta, che presenta due classi derivate non astratte, Square e Circle. Nell'esempio viene illustrato come utilizzare le classi, i metodi e le proprietà astratte. Nell'esempio la forma della classe astratta rappresenta gli elementi comuni del cerchio e del quadrato delle entità concrete. Le funzionalità comuni di tutte le forme (in un sistema di coordinate bidimensionali) vengono ricavate nella classe Shape: la posizione sulla griglia, un angolo di rotazione e le proprietà area e perimetrale. È possibile eseguirne l'override, ad eccezione della posizione, il comportamento del quale le singole forme non possono essere modificate.

Il metodo di rotazione può essere sottoposto a override, come nella classe Circle, che è invariante di rotazione a causa della relativa simmetria. Quindi, nella classe Circle, il metodo di rotazione viene sostituito da un metodo che non esegue alcuna operazione.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Output:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Vedere anche

- [Classi](classes.md)
- [Membri](./members/index.md)
- [Metodi](./members/methods.md)
- [Proprietà](./members/Properties.md)
