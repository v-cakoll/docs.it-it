---
title: Tipi
description: Informazioni sui tipi usati in e sul modo F# F# in cui i tipi vengono denominati e descritti.
ms.date: 05/16/2016
ms.openlocfilehash: 70d79525318c8d2eb0711d6a1b50be1ac0cf0226
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348208"
---
# <a name="f-types"></a>Tipi F#

In questo argomento vengono descritti i tipi utilizzati in F# e il F# modo in cui i tipi vengono denominati e descritti.

## <a name="summary-of-f-types"></a>Riepilogo dei F# tipi

Alcuni tipi sono considerati *tipi primitivi*, ad esempio il tipo booleano `bool` e i tipi a virgola mobile e integrali di diverse dimensioni, che includono i tipi per byte e caratteri. Questi tipi sono descritti in [tipi primitivi](basic-types.md).

Altri tipi incorporati nella lingua includono Tuple, elenchi, matrici, sequenze, record e unioni discriminate. Se si ha esperienza con altri linguaggi .NET e si sta F#imparando, è necessario leggere gli argomenti per ognuno di questi tipi. I collegamenti ad altre informazioni su questi tipi sono inclusi nella sezione [argomenti correlati](https://msdn.microsoft.com/library/#rel) di questo argomento. Questi F#tipi specifici supportano gli stili di programmazione comuni ai linguaggi di programmazione funzionale. Molti di questi tipi hanno moduli associati nella F# libreria che supportano operazioni comuni su questi tipi.

Il tipo di una funzione include informazioni sui tipi di parametro e sul tipo restituito.

Il .NET Framework è l'origine di tipi di oggetto, tipi di interfaccia, tipi delegati e altri. È possibile definire i propri tipi di oggetto esattamente come in qualsiasi altro linguaggio .NET.

Inoltre, F# il codice può definire alias, ovvero *abbreviazioni di tipo*denominate, che sono nomi alternativi per i tipi. È possibile usare le abbreviazioni di tipo quando il tipo potrebbe cambiare in futuro e si vuole evitare di modificare il codice che dipende dal tipo. In alternativa, è possibile utilizzare un'abbreviazione di tipo come nome descrittivo per un tipo in grado di semplificare la lettura e la comprensione del codice.

F#fornisce tipi di raccolta utili progettati con la programmazione funzionale. L'uso di questi tipi di raccolta consente di scrivere codice più funzionale nello stile. Per ulteriori informazioni, vedere [ F# tipi di raccolta](fsharp-collection-types.md).

## <a name="syntax-for-types"></a>Sintassi per i tipi

Nel F# codice è spesso necessario scrivere i nomi dei tipi. Ogni tipo ha una forma sintattica e si usano queste forme sintattiche in annotazioni di tipo, dichiarazioni di metodi astratti, dichiarazioni di delegati, firme e altri costrutti. Ogni volta che si dichiara un nuovo costrutto di programma nell'interprete, l'interprete stampa il nome del costrutto e la sintassi per il relativo tipo. Questa sintassi potrebbe essere semplicemente un identificatore per un tipo definito dall'utente o un identificatore incorporato, ad esempio per `int` o `string`, ma per i tipi più complessi la sintassi è più complessa.

Nella tabella seguente vengono illustrati gli aspetti della sintassi F# del tipo per i tipi.

|Tipo di|Sintassi del tipo|Esempi|
|----|-----------|--------|
|tipo primitivo|*type-name*|`int`<br /><br />`float`<br /><br />`string`|
|tipo aggregato (classe, struttura, Unione, record, enumerazione e così via)|*type-name*|`System.DateTime`<br /><br />`Color`|
|abbreviazione di tipo|*tipo-abbreviazione-nome*|`bigint`|
|tipo completo|*namespaces.type-name*<br /><br />oppure<br /><br />*modules.type-name*<br /><br />oppure<br /><br />*namespaces.modules.type-name*|`System.IO.StreamWriter`|
|Matrice di oggetti .|*Type-Name*[] o<br /><br />matrice *di nomi di tipo*|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|matrice bidimensionale|*nome-tipo*[,]|`int[,]`<br /><br />`float[,]`|
|matrice tridimensionale|*nome-tipo*[,,]|`float[,,]`|
|tuple|*tipo-name1* &#42; *-name2* ...|Ad esempio, `(1,'b',3)` è di tipo `int * char * int`|
|tipo generico|*tipo-parametro* *generico-tipo-nome*<br /><br />oppure<br /><br />*generic-type-name*&lt;*type-parameter-list*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|tipo costruito (un tipo generico con un argomento di tipo specifico fornito)|*tipo-argomento* *generico-tipo-nome*<br /><br />oppure<br /><br />*generic-type-name*&lt;*type-argument-list*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|tipo di funzione con un solo parametro|*Parameter-tipo1* -&gt; *tipo restituito*|Funzione che accetta un `int` e restituisce un `string` di tipo `int -> string`|
|tipo di funzione con più parametri|*Parameter-tipo1* -&gt; *parametro-tipo2* -&gt;...-&gt; *tipo restituito*|Funzione che accetta un `int` e un `float` e restituisce un `string` di tipo `int -> float -> string`|
|funzione di ordine superiore come parametro|(*tipo di funzione*)|il tipo di `List.map` è `('a -> 'b) -> 'a list -> 'b list`|
|delegate|Delegato di *tipo funzione*|`delegate of unit -> int`|
|tipo flessibile|*nome tipo* #|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Argomenti correlati

|Argomento|Descrizione|
|-----|-----------|
|[Tipi primitivi](basic-types.md)|Vengono descritti i tipi semplici incorporati, ad esempio i tipi integrali, il tipo booleano e i tipi di carattere.|
|[Tipo di unità](unit-type.md)|Descrive il tipo `unit`, un tipo con un valore e indicato da (); equivale a `void` in C# e `Nothing` in Visual Basic.|
|[Tuple](tuples.md)|Descrive il tipo di tupla, un tipo costituito da valori associati di qualsiasi tipo raggruppati in coppie, triple, quadruple e così via.|
|[Opzioni](options.md)|Descrive il tipo di opzione, un tipo che può avere un valore o essere vuoto.|
|[Elenchi](lists.md)|Vengono descritti gli elenchi, che sono serie ordinata e non modificabile di elementi tutti dello stesso tipo.|
|[Matrici](arrays.md)|Descrive le matrici, che sono set ordinati di elementi modificabili dello stesso tipo che occupano un blocco di memoria contiguo e sono di dimensioni fisse.|
|[Sequenze](sequences.md)|Descrive il tipo di sequenza, che rappresenta una serie logica di valori. i singoli valori vengono calcolati solo se necessario.|
|[Record](records.md)|Descrive il tipo di record, una piccola aggregazione di valori denominati.|
|[Unioni discriminate](discriminated-unions.md)|Descrive il tipo di unione discriminata, un tipo i cui valori possono essere uno qualsiasi di un set di tipi possibili.|
|[Funzioni](./functions/index.md)|Descrive i valori di funzione.|
|[Classi](classes.md)|Descrive il tipo di classe, un tipo di oggetto che corrisponde a un tipo di riferimento .NET. I tipi di classe possono contenere membri, proprietà, interfacce implementate e un tipo di base.|
|[Strutture](structures.md)|Descrive il tipo di `struct`, un tipo di oggetto che corrisponde a un tipo di valore .NET. Il tipo di `struct` rappresenta in genere una piccola aggregazione di dati.|
|[Interfacce](interfaces.md)|Descrive i tipi di interfaccia, che sono tipi che rappresentano un set di membri che forniscono determinate funzionalità ma che non contengono dati. Un tipo di interfaccia deve essere implementato da un tipo di oggetto per essere utile.|
|[Delegati](delegates.md)|Descrive il tipo delegato, che rappresenta una funzione come oggetto.|
|[Enumerazioni](enumerations.md)|Descrive i tipi di enumerazione i cui valori appartengono a un set di valori denominati.|
|[Attributi](attributes.md)|Descrive gli attributi, che vengono usati per specificare i metadati per un altro tipo.|
|[Tipi di eccezione](./exception-handling/exception-types.md)|Descrive le eccezioni che specificano le informazioni sull'errore.|
