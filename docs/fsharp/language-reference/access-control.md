---
title: Controllo di accesso (F#)
description: "Informazioni su come controllare l'accesso agli elementi di programmazione, ad esempio i tipi, metodi e funzioni, il linguaggio di programmazione F #."
ms.date: 05/16/2016
ms.openlocfilehash: 66a260d326acf07391e3775e5a7853654b4feee4
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803974"
---
# <a name="access-control"></a>Controllo di accesso

*Controllo di accesso* fa riferimento alla dichiarazione di client in cui è possono usare determinati elementi di programma, ad esempio i tipi, metodi e funzioni.

## <a name="basics-of-access-control"></a>Nozioni di base del controllo di accesso

In F #, identificatori del controllo di accesso `public`, `internal`, e `private` è applicabile ai moduli, tipi, metodi, le definizioni di valore, funzioni, proprietà e i campi espliciti.

- `public` indica che l'entità sia accessibile da tutti i chiamanti.

- `internal` indica che l'entità sia accessibile solo dallo stesso assembly.

- `private` indica che l'entità sia accessibile solo dal tipo o modulo che lo contiene.

>[!NOTE]
L'identificatore di accesso `protected` non viene usato in F #, anche se è accettabile se si utilizzano tipi creati in linguaggi che supportano `protected` accesso. Pertanto, se si esegue l'override di un metodo protetto, il metodo rimane accessibile solo all'interno della classe e i relativi discendenti.

In generale, l'identificatore viene inserito davanti al nome dell'entità, tranne quando un `mutable` o `inline` identificatore viene usato, che appare dopo l'identificatore del controllo di accesso.

Se non viene usato alcun identificatore di accesso, il valore predefinito è `public`, ad eccezione di `let` associazioni in un tipo, che sono sempre `private` al tipo.

Le firme in F # forniscono un altro meccanismo per controllare l'accesso agli elementi del programma F #. Le firme non sono necessarie per il controllo di accesso. Per altre informazioni, vedere [Firme](signatures.md).

## <a name="rules-for-access-control"></a>Regole di controllo di accesso

Controllo di accesso è soggetto alle regole seguenti:

- Le dichiarazioni di ereditarietà (vale a dire l'uso di `inherit` per specificare una classe base per una classe), le dichiarazioni (ovvero, la specifica che una classe implementa un'interfaccia) di interfaccia e l'astrazione membri hanno sempre la stessa accessibilità del tipo di inclusione. Pertanto, un identificatore di controllo di accesso non può essere utilizzato su questi costrutti.

- Accessibilità per singoli case in un'unione discriminata è determinato dall'accessibilità dell'unione discriminata stesso. Un particolare case di unione è l'unione stessa non è meno accessibile.

- Accessibilità per i singoli campi di un tipo di record non è determinata dall'accessibilità del record stesso. Vale a dire, un'etichetta di record specifico è non meno accessibile il record stesso.

## <a name="example"></a>Esempio

Il codice seguente viene illustrato l'utilizzo di identificatori di controllo di accesso. Sono disponibili due file nel progetto `Module1.fs` e `Module2.fs`. Ogni file in modo implicito è un modulo. Pertanto, sono presenti due moduli `Module1` e `Module2`. Un tipo privato e un tipo interno sono definiti nel `Module1`. Il tipo privato non è accessibile da `Module2`, ma è di tipo interno.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]

Il codice seguente verifica l'accessibilità dei tipi creati `Module1.fs`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
- [Firme](signatures.md)
