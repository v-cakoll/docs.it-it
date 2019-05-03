---
title: Classi astratte
description: Informazioni su F# classi, che lascia alcuni o tutti i membri non implementati astratte e rappresenta funzionalità comuni a diversi set di tipi di oggetto.
ms.date: 05/16/2016
ms.openlocfilehash: fecd3b2d550c6b8f59fa614f5d00c5f730a4896a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772775"
---
# <a name="abstract-classes"></a>Classi astratte

*Classi astratte* sono classi che lasciano alcuni o tutti i membri non implementati, in modo che le implementazioni possono essere fornite dalle classi derivate.

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

Nella programmazione orientata agli oggetti, una classe astratta viene usata come classe di base di una gerarchia e rappresenta funzionalità comuni a diversi set di tipi di oggetto. Come il nome "abstract" implica, classi astratte spesso non corrispondono direttamente a entità concrete nel dominio del problema. Tuttavia, rappresentano cosa molte entità concreta diverse hanno in comune.

Classi astratte devono avere la `AbstractClass` attributo. Possono avere implementato e non implementati i membri. L'uso del periodo di validità *astratto* quando viene applicato a una classe è analogo a quello in altri linguaggi .NET; tuttavia, l'utilizzo del termine *astratta* quando applicato a metodi (e proprietà) è lievemente differente in F# dal relativo utilizzo in altri linguaggi .NET. In F#, quando un metodo è contrassegnato con il `abstract` (parola chiave), significa che un membro dispone di una voce, nota come un *slot di distribuzione virtuale*, nella tabella interna di funzioni virtuali per quel tipo. In altre parole, il metodo è virtuale, anche se il `virtual` parola chiave non viene usato nel F# lingua. La parola chiave `abstract` viene usato nei metodi virtuali, indipendentemente dal fatto che il metodo è implementato. La dichiarazione di uno slot di distribuzione virtuale è separata dalla definizione di un metodo per tale slot di distribuzione. Pertanto, il F# equivalente di una dichiarazione di metodo virtuale e una definizione in un altro linguaggio .NET è una combinazione di una dichiarazione di metodo astratto e una definizione separata, con il `default` parola chiave o il `override` (parola chiave). Per altre informazioni ed esempi, vedere [metodi](members/methods.md).

Una classe verrà considerata astratta solo se sono presenti metodi astratti che vengono dichiarati ma non definiti. Di conseguenza, le classi con metodi astratti non sono necessariamente classi astratte. A meno che una classe ha definito i metodi astratti, non usare la **AbstractClass** attributo.

Nella sintassi precedente *modificatore di accessibilità* può essere `public`, `private` o `internal`. Per altre informazioni, vedere [Controllo di accesso](access-control.md).

Come con gli altri tipi di classi astratte possono avere una classe di base e uno o più interfacce di base. Ogni classe di base o interfaccia viene visualizzato in una riga separata con il `inherit` (parola chiave).

La definizione del tipo di una classe astratta può contenere membri completamente definiti, ma può anche contenere membri astratti. La sintassi per i membri astratti viene visualizzata separatamente nella sintassi precedente. In questa sintassi, il *firma del tipo* di un membro è un elenco che contiene i tipi di parametro in ordine e i tipi restituiti, separato da `->` i token e/o `*` token come appropriato per sottoposte a currying e in forma di tupla parametri. La sintassi per le firme del tipo di membro astratto è analoghi a quelli utilizzati nei file di firma visualizzata da IntelliSense nell'Editor di codice di Visual Studio.

Il codice seguente illustra una classe astratta, forma, che dispone di due classi non astratte derivate, Square e Circle. Nell'esempio viene illustrato come utilizzare le proprietà, metodi e classi astratte. Nell'esempio, la forma classe astratta rappresenta gli elementi comuni del cerchio entità concreta e quadrato. Le funzionalità comuni di tutte le forme (in un sistema di coordinate bidimensionale) vengono estratte nella classe Shape: la posizione della griglia, l'angolo di rotazione e le proprietà di area e perimetro. Questi può essere sottoposto a override, ad eccezione di posizione, il comportamento di cui non è possibile modificare le singole forme.

Il metodo di rotazione può eseguire l'override, come la classe cerchio, ovvero la rotazione invariante a causa della sua simmetria. Quindi, nella classe Circle, il metodo di rotazione viene sostituito da un metodo che non esegue alcuna operazione.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Output:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Vedere anche

- [Classi](classes.md)
- [Membri](members/index.md)
- [Metodi](members/methods.md)
- [Proprietà](members/Properties.md)