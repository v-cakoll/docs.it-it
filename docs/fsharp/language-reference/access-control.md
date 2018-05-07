---
title: Controllo di accesso (F#)
description: "Informazioni su come controllare l'accesso a elementi di programmazione, ad esempio tipi, metodi e funzioni, il linguaggio di programmazione F #."
ms.date: 05/16/2016
ms.openlocfilehash: 0a5cc1faa1aef343aaca0abb0c42a0dd9a52fcbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="access-control"></a>Controllo di accesso

*Il controllo degli accessi* fa riferimento alla dichiarazione quali client possono utilizzare alcuni elementi di programma, ad esempio i tipi, metodi e funzioni.


## <a name="basics-of-access-control"></a>Nozioni di base del controllo di accesso
In F #, identificatori del controllo di accesso `public`, `internal`, e `private` può essere applicato ai moduli, tipi, metodi, le definizioni di valore, funzioni, proprietà e i campi espliciti.


- `public` indica che l'entità sia accessibile da tutti i chiamanti.

- `internal` indica che l'entità sia accessibile solo dallo stesso assembly.

- `private` indica che l'entità sia accessibile solo dal tipo o modulo che lo contiene.


>[!NOTE] 
L'identificatore di accesso `protected` non viene usato in F #, ma è accettabile se si utilizzano tipi creati in linguaggi che supportano `protected` accesso. Pertanto, se si esegue l'override di un metodo protetto, il metodo rimane accessibile solo all'interno della classe e i relativi discendenti.

In generale, l'identificatore è posizionato davanti al nome dell'entità, tranne quando una `mutable` o `inline` identificatore viene usato, che appare dopo l'identificatore del controllo di accesso.

Se viene utilizzato alcun identificatore di accesso, il valore predefinito è `public`, ad eccezione di `let` binding in un tipo, che sono sempre `private` al tipo.

Le firme in F # è un altro meccanismo per controllare l'accesso agli elementi del programma F #. Le firme non sono necessari per il controllo di accesso. Per altre informazioni, vedere [Firme](signatures.md).


## <a name="rules-for-access-control"></a>Regole per il controllo di accesso
Controllo di accesso è soggetto alle seguenti regole:


- Le dichiarazioni di ereditarietà (ovvero, l'utilizzo di `inherit` per specificare una classe base per una classe), le dichiarazioni (ovvero, la specifica che una classe implementa un'interfaccia) di interfaccia e l'astrazione membri hanno sempre la stessa accessibilità del tipo di inclusione. Pertanto, un identificatore di controllo di accesso può essere usato in questi costrutti.

- Singoli case in un'unione discriminata non possono contenere i propri modificatori di controllo di accesso separati dal tipo di unione.

- I singoli campi di un tipo di record non possono contenere i propri modificatori di controllo di accesso separati dal tipo di record.


## <a name="example"></a>Esempio
Il codice seguente viene illustrato l'utilizzo di identificatori di controllo di accesso. Sono disponibili due file del progetto, `Module1.fs` e `Module2.fs`. Ogni file in modo implicito è un modulo. Pertanto, sono presenti due moduli, `Module1` e `Module2`. Un tipo privato e un tipo interno sono definiti nel `Module1`. Il tipo privato non sono accessibili da `Module2`, ma è di tipo interno.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
Il codice seguente controlla l'accessibilità di tipi creati in `Module1.fs`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)

[Firme](signatures.md)
