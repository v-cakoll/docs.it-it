---
title: Tipi e variabili C# - Panoramica del linguaggio C#
description: Informazioni sulla definizione di tipi e la dichiarazione di variabili nel linguaggio C#
ms.date: 02/25/2020
ms.assetid: f8a8051e-0049-43f1-b594-9c84cc7b1224
ms.openlocfilehash: b2a5255a243c12543a1cd59b5724b6c826306e04
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159091"
---
# <a name="types-and-variables"></a>Tipi e variabili

In C# esistono due generi di tipi: *tipi valore* e *tipi riferimento*. Le variabili dei tipi valore contengono direttamente i propri dati, mentre le variabili dei tipi riferimento archiviano i riferimenti ai propri dati, noti come oggetti. Con i tipi di riferimento, è possibile che due variabili facciano riferimento allo stesso oggetto e pertanto le operazioni su una variabile influiscano sull'oggetto a cui fa riferimento l'altra variabile. Con i tipi valore, ogni variabile ha una propria copia dei dati e non è possibile che le operazioni su uno influiscano sull'altro (ad eccezione delle variabili di parametro `ref` e `out`).

I tipi valore di C# sono ulteriormente suddivisi in *tipi semplici*, *tipi enum*, *tipi struct* e *tipi valore nullable*. I tipi riferimento di C# sono ulteriormente suddivisi in *tipi classe*, *tipi interfaccia*, *tipi matrice* e *tipi delegato*.

Nella struttura seguente viene fornita una panoramica C#del sistema di tipi di.

- [Tipi di valore][ValueTypes]
  - [Tipi semplici][SimpleTypes]
    - Signed Integer: `sbyte`, `short`, `int`,`long`
    - Unsigned Integer: `byte`, `ushort`, `uint`,`ulong`
    - Caratteri Unicode: `char`
    - File binario IEEE a virgola mobile: `float`, `double`
    - Decimale ad alta precisione a virgola mobile: `decimal`
    - Booleano: `bool`
  - [Tipi enum][EnumTypes]
    - Tipi definiti dall'utente nel formato `enum E {...}`
  - [Tipi struct][StructTypes]
    - Tipi definiti dall'utente nel formato `struct S {...}`
  - [Tipi valore nullable][NullableTypes]
    - Estensioni di tutti gli altri tipi valore con un valore `null`
- [Tipi riferimento][ReferenceTypes]
  - [Tipi classe][ClassTypes]
    - Classe di base principale di tutti gli altri tipi: `object`
    - Stringhe Unicode: `string`
    - Tipi definiti dall'utente nel formato `class C {...}`
  - [Tipi interfaccia][InterfaceTypes]
    - Tipi definiti dall'utente nel formato `interface I {...}`
  - [Tipi di matrice][ArrayTypes]
    - Unidimensionale e multidimensionale, ad esempio `int[]` e `int[,]`
  - [Tipi delegato][DelegateTypes]
    - Tipi definiti dall'utente nel formato `delegate int D(...)`

[ValueTypes]: ../language-reference/builtin-types/value-types.md
[SimpleTypes]: ../language-reference/builtin-types/value-types.md#built-in-value-types
[EnumTypes]: ../language-reference/builtin-types/enum.md
[StructTypes]: ../language-reference/builtin-types/struct.md
[NullableTypes]: ../language-reference/builtin-types/nullable-value-types.md
[ReferenceTypes]: ../language-reference/keywords/reference-types.md
[ClassTypes]: ../language-reference/keywords/class.md
[InterfaceTypes]: ../language-reference/keywords/interface.md
[DelegateTypes]: ../language-reference/keywords/delegate.md
[ArrayTypes]: ../programming-guide/arrays/index.md

Per altre informazioni sui tipi numerici, vedere la [tabella dei tipi integrali](../language-reference/builtin-types/integral-numeric-types.md) e la [tabella dei tipi a virgola mobile](../language-reference/builtin-types/floating-point-numeric-types.md).

Il tipo `bool` di C# viene usato per rappresentare valori booleani, ovvero valori che sono `true` o `false`.

Per l'elaborazione di caratteri e stringhe, in C# viene usata la codifica Unicode. Il tipo `char` rappresenta un'unità di codice UTF-16, mentre il tipo `string` rappresenta una sequenza di unità di codice UTF-16.

I programmi C# usano le *dichiarazioni di tipo* per creare nuovi tipi. Una dichiarazione di tipo consente di specificare il nome e i membri del nuovo tipo. Cinque delle categorie di tipi di C# possono essere definite dall'utente: tipi classe, tipi struct, tipi interfaccia, tipi enum e tipi delegato.

Un tipo `class` definisce una struttura dati contenente membri dati (campi) e membri funzione (metodi, proprietà e altro). I tipi classe supportano l'ereditarietà singola e il polimorfismo, meccanismi in base ai quali le classi derivate possono estendere e specializzare le classi di base.

Un tipo `struct` è simile a un tipo classe in quanto rappresenta una struttura con membri dati e membri funzione. Tuttavia, a differenza delle classi, gli struct sono tipi di valore e in genere non richiedono l'allocazione dell'heap. I tipi struct non supportano l'ereditarietà specificata dall'utente e tutti i tipi struct ereditano implicitamente dal tipo `object`.

Un tipo `interface` definisce un contratto come un set denominato di membri funzione pubblici. Un tipo `class` o `struct` che implementa un tipo `interface` deve fornire le implementazioni dei membri funzione dell'interfaccia. Un tipo `interface` può ereditare da più interfacce di base e un tipo `class` o `struct` può implementare più interfacce.

Un tipo `delegate` rappresenta i riferimenti ai metodi, con un elenco di parametri e un tipo restituito particolari. I delegati consentono di trattare i metodi come entità che è possibile assegnare a variabili e passare come parametri. I delegati sono analoghi ai tipi funzione forniti dai linguaggi funzionali. Sono anche simili al concetto di puntatori a funzione disponibili in altri linguaggi. A differenza dei puntatori a funzione, i delegati sono orientati agli oggetti e indipendenti dai tipi.

I tipi `class`, `struct`, `interface`e `delegate` supportano tutti i generics, in base ai quali possono essere parametrizzati con altri tipi.

Un tipo `enum` è un tipo distinto con costanti denominate. Ogni tipo `enum` ha un tipo sottostante, che deve essere uno degli otto tipi integrali. Il set di valori di un tipo `enum` coincide con il set di valori del tipo sottostante.

C# supporta matrici unidimensionali e multidimensionali di qualsiasi tipo. A differenza dei tipi elencati in precedenza, i tipi di matrice non devono essere dichiarati prima di poter essere usati. Al contrario, i tipi matrice vengono costruiti facendo seguire a un nome di tipo delle parentesi quadre. Ad esempio, `int[]` è una matrice unidimensionale di `int`, `int[,]` è una matrice bidimensionale di `int` e `int[][]` è una matrice unidimensionale di matrici unidimensionali di `int`.

Anche i tipi di valore nullable non devono essere dichiarati prima di poter essere usati. Per ogni tipo di valore non nullable `T`, esiste un tipo di valore nullable corrispondente `T?`, che può avere un valore aggiuntivo, `null`. Ad esempio, `int?` è un tipo che può contenere qualsiasi Integer a 32 bit o il valore `null`.

Il sistema di tipi di C# è unificato in modo tale che un valore di qualsiasi tipo può essere trattato come un `object`. In C# ogni tipo deriva direttamente o indirettamente dal tipo classe `object` e `object` è la classe di base principale di tutti i tipi. I valori dei tipi riferimento vengono trattati come oggetti semplicemente visualizzando tali valori come tipi `object`. I valori dei tipi valore vengono trattati come oggetti mediante l'esecuzione di operazioni di *boxing* e *unboxing*. Nell'esempio seguente un valore `int` viene convertito in `object` e quindi convertito nuovamente in `int`.

[!code-csharp[Boxing](../../../samples/snippets/csharp/tour/types-and-variables/Program.cs#L1-L10)]

Quando un valore di un tipo valore viene convertito in un tipo `object`, un'istanza di `object`, denominata anche "box", viene allocata per contenere tale valore. Quest'ultimo viene copiato nel box. Al contrario, quando viene eseguito il cast di un riferimento `object` a un tipo valore, il sistema effettua un controllo per verificare che l'`object` a cui viene fatto riferimento sia un box del tipo valore corretto. Se il controllo ha esito positivo, il valore presente nel box viene copiato.

Con il sistema di tipi unificato di C#, i tipi valore possono diventare oggetti "su richiesta". Grazie all'unificazione, le librerie generiche che usano il tipo `object` possono essere usate con entrambi i tipi riferimento e valore.

In C# sono disponibili diversi tipi di *variabili*, inclusi campi, elementi matrice, variabili locali e parametri. Le variabili rappresentano posizioni di archiviazione e ogni variabile dispone di un tipo che determina quali valori possono essere archiviati nella variabile stessa, come illustrato di seguito.

- Tipo valore non-nullable
  - Valore esattamente del tipo indicato
- Tipo valore nullable
  - Valore `null` o valore esattamente del tipo indicato
- object
  - Riferimento `null`, riferimento a un oggetto di qualsiasi tipo riferimento oppure riferimento a un valore boxed di qualsiasi tipo valore
- Tipo classe
  - Riferimento `null`, riferimento a un'istanza del tipo classe oppure riferimento a un'istanza di una classe derivata dal tipo classe
- Tipo interfaccia
  - Riferimento `null`, riferimento a un'istanza di un tipo classe che implementa il tipo interfaccia oppure riferimento a un valore boxed di un tipo valore che implementa il tipo interfaccia
- Tipo matrice
  - Riferimento `null`, riferimento a un'istanza del tipo matrice oppure riferimento a un'istanza di un tipo matrice compatibile
- Tipo delegato
  - Riferimento `null` oppure riferimento a un'istanza di un tipo delegato compatibile

> [!div class="step-by-step"]
> [Precedente](program-structure.md)
> [Successivo](expressions.md)
