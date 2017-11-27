---
title: Classi astratte (F#)
description: "Informazioni su F # classi astratte, in cui alcuni o tutti i membri non implementata e rappresentano una funzionalità comune di un set di tipi di oggetto."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 209bcca70318db59506011b1f2bb74a09bf3814a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="abstract-classes"></a>Classi astratte

*Classi astratte* sono classi in cui alcuni o tutti i membri non implementati, in modo che le implementazioni possono essere fornite dalle classi derivate.

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
Nella programmazione orientata agli oggetti, una classe astratta viene utilizzata come classe di base di una gerarchia e rappresenta la funzionalità comune di un set di tipi di oggetto. Come suggerito dal nome "classe", classi astratte spesso non corrispondono direttamente a entità concrete nel dominio del problema. Tuttavia, che rappresentano le numerose entità concrete diverse hanno in comune.

Le classi astratte devono avere la `AbstractClass` attributo. Possono avere implementato e i membri di non implementata. L'utilizzo del termine *astratta* quando applicato a una classe è uguale a quello di altri linguaggi .NET; tuttavia, l'utilizzo del termine *astratta* quando applicata a (metodi e proprietà) è leggermente diverso in F # da relativo utilizzare in altri linguaggi .NET. In F #, quando un metodo è contrassegnato con il `abstract` (parola chiave), significa che un membro dispone di una voce, nota come un *slot di invio virtuale*, nella tabella interna di funzioni virtuali per quel tipo. In altre parole, il metodo è virtuale, anche se il `virtual` parola chiave non viene usato nel linguaggio F #. La parola chiave `abstract` viene usato nei metodi virtuali, indipendentemente dal fatto che il metodo è implementato. La dichiarazione di uno slot di distribuzione virtuale è separata dalla definizione di un metodo per tale slot di distribuzione. Pertanto, l'equivalente di una dichiarazione di metodo virtuale e la definizione di un altro linguaggio .NET F # è una combinazione di una dichiarazione di metodo astratto e una definizione separata, con la `default` parola chiave o `override` (parola chiave). Per ulteriori informazioni ed esempi, vedere [metodi](members/methods.md).

Una classe è considerata astratta solo se esistono metodi astratti dichiarati, ma non è definiti. Pertanto, le classi che dispongono di metodi astratti non sono necessariamente classi astratte. A meno che una classe ha definito i metodi astratti, non utilizzare il **AbstractClass** attributo.

Nella sintassi precedente, *modificatore di accessibilità* può essere `public`, `private` o `internal`. Per altre informazioni, vedere [Controllo di accesso](access-control.md).

Come con altri tipi, classi astratte possono avere una classe di base e uno o più interfacce di base. Ogni classe di base o interfaccia, viene visualizzato in una riga separata, insieme con il `inherit` (parola chiave).

La definizione del tipo di una classe astratta può contenere membri completamente definiti, ma può anche contenere membri astratti. La sintassi per i membri astratti viene visualizzata separatamente nella sintassi precedente. In questa sintassi, il *la firma del tipo* di un membro è un elenco che contiene i tipi di parametro in ordine e i tipi restituiti, separato da `->` token e/o `*` token come appropriato per sottoposte a currying e tupla parametri. La sintassi per le firme del tipo di membro astratto è quello utilizzato nel file di firma e visualizzata da IntelliSense nell'Editor di codice di Visual Studio.

Il codice seguente viene illustrata una classe astratta, forma, che dispone di due classi non astratte derivate, Square e Circle. Nell'esempio viene illustrato come utilizzare le proprietà, metodi e classi astratte. Nell'esempio, la forma della classe astratta rappresenta gli elementi comuni delle entità concrete circle e square. Le funzionalità comuni di tutte le forme (in un sistema di coordinate bidimensionale) vengono estratte nella classe Shape: la posizione nella griglia, l'angolo di rotazione e le proprietà di area e il perimetro. Questi può essere sottoposto a override, ad eccezione di posizione, il comportamento di cui non è possibile modificare le singole forme.

Il metodo di rotazione può essere sottoposto a override, come la classe di cerchio, che è invariante rispetto alla rotazione a causa della sua simmetria. Nella classe Circle, pertanto il metodo di rotazione viene sostituito da un metodo che non esegue alcuna operazione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Output:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Vedere anche
[Classi](classes.md)

[Membri](members/index.md)

[Metodi](members/methods.md)

[Proprietà](members/Properties.md)
