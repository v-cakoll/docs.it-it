---
title: Tipi F#
description: Informazioni sui tipi utilizzabili in F# e in che modo F# sono denominati e descritti i tipi.
ms.date: 05/16/2016
ms.openlocfilehash: b48376c80b48df210bf7bc699a769d40fec60864
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934641"
---
# <a name="f-types"></a>Tipi F#

In questo argomento vengono descritti i tipi usati in F# e in che modo F# sono denominati e descritti i tipi.

## <a name="summary-of-f-types"></a>Riepilogo di F# tipi
Alcuni tipi sono considerati *i tipi primitivi*, ad esempio il tipo booleano `bool` e tipi a virgola mobile e integrali di diverse dimensioni, che includono i tipi di caratteri e i byte. Questi tipi sono descritti [i tipi primitivi](primitive-types.md).

Altri tipi che vengono integrate nel linguaggio includono le tuple, elenchi, matrici, le sequenze, record e unioni discriminate. Se si ha esperienza con altri linguaggi .NET e vengono learning F#, è consigliabile leggere gli argomenti per ognuno di questi tipi. In sono inclusi collegamenti a ulteriori informazioni su questi tipi di [argomenti correlati](https://msdn.microsoft.com/library/#rel) sezione di questo argomento. Questi F#-tipi specifici supportano gli stili di programmazione comuni a linguaggi di programmazione funzionale. Molti di questi tipi sono associati i moduli di F# libreria che supportano le operazioni comuni su questi tipi.

Il tipo di una funzione include informazioni sui tipi di parametro e tipo restituito.

.NET Framework è l'origine di tipi di oggetto, tipi interfaccia, tipi delegati e ad altri utenti. Proprio come in qualsiasi altro linguaggio .NET, è possibile definire i tipi di oggetto.

Inoltre, F# codice è possibile definire gli alias, sono denominati *abbreviazioni di tipo*, che sono nomi alternativi per i tipi. È possibile usare le abbreviazioni dei tipi quando il tipo potrebbe cambiare in futuro e si vuole evitare di modificare il codice che dipende dal tipo. In alternativa, è possibile usare un'abbreviazione di tipo come un nome descrittivo per un tipo che può rendere più semplice da leggere e comprendere codice.

F#Fornisce tipi di raccolta utile che sono progettati con la programmazione funzionale in considerazione. Utilizzo di questi tipi di raccolta consente di scrivere codice che è più funziona nello stile. Per altre informazioni, vedere [ F# tipi di raccolte](fsharp-collection-types.md).

## <a name="syntax-for-types"></a>Sintassi per i tipi
In F# codice, spesso è necessario scrivere i nomi dei tipi. Ogni tipo ha una forma sintattica e si usano queste forme in annotazioni del tipo, le dichiarazioni di metodo astratto, le dichiarazioni delegate, firme e altri costrutti sintattiche. Ogni volta che si dichiara un nuovo costrutto di programma nell'interprete, l'interprete stampa il nome del costrutto e la sintassi per il relativo tipo. Questa sintassi può essere solo un identificatore per un tipo definito dall'utente o un identificatore incorporato, ad esempio le `int` o `string`, ma per i tipi più complessi, la sintassi è più complessa.

La tabella seguente illustra gli aspetti della sintassi del tipo per F# tipi.

|Tipo|Sintassi di tipo|Esempi|
|----|-----------|--------|
|tipo primitivo|*type-name*|`int`<br /><br />`float`<br /><br />`string`|
|tipo di aggregazione (classe, struttura, unione, record, enum e così via)|*type-name*|`System.DateTime`<br /><br />`Color`|
|abbreviazione di tipo|*type-abbreviation-name*|`bigint`|
|nome completo del tipo|*namespaces.type-name*<br /><br />oppure<br /><br />*modules.type-name*<br /><br />oppure<br /><br />*namespaces.modules.type-name*|`System.IO.StreamWriter`|
|array|*nome del tipo*[] o<br /><br />*nome del tipo* matrice|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|matrice bidimensionale|*type-name*[,]|`int[,]`<br /><br />`float[,]`|
|Matrice tridimensionale|*type-name*[,,]|`float[,,]`|
|tuple|*type-name1* &#42; *type-name2* ...|Ad esempio, `(1,'b',3)` ha tipo `int * char * int`|
|tipo generico|*type-parameter* *generic-type-name*<br /><br />oppure<br /><br />*generic-type-name*&lt;*type-parameter-list*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|costruito (un tipo generico che ha un argomento di tipo specifico fornito)|*type-argument* *generic-type-name*<br /><br />oppure<br /><br />*generic-type-name*&lt;*type-argument-list*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|tipo di funzione che ha un parametro singolo|*parameter-type1* -&gt; *return-type*|Una funzione che accetta un `int` e restituisce un `string` ha tipo `int -> string`|
|tipo di funzione che ha più parametri|*parametro-tipo1*  - &gt; *parametro type2*  - &gt; ... -&gt; *tipo restituito*|Una funzione che accetta un `int` e una `float` e restituisce un `string` ha tipo `int -> float -> string`|
|funzione di ordine superiore come parametro|(*function-type*)|`List.map` è di tipo `('a -> 'b) -> 'a list -> 'b list`|
|delegato|delegato di *-tipo di funzione*|`delegate of unit -> int`|
|tipo flessibile|#*nome del tipo*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Argomenti correlati

|Argomento|Descrizione|
|-----|-----------|
|[Tipi primitivi](primitive-types.md)|Descrive i tipi semplici incorporati, ad esempio i tipi integrali, il tipo booleano e tipi di carattere.|
|[Tipo di unità](unit-type.md)|Descrive la `unit` tipo, un tipo che ha un valore e viene indicato da (); equivalente alla `void` in C# e `Nothing` in Visual Basic.|
|[Tuple](tuples.md)|Descrive il tipo di tupla, un tipo che è costituito da valori associati di qualsiasi tipo raggruppati in coppie, Triple, quattro elementi e così via.|
|[Opzioni](options.md)|Descrive il tipo di opzione, un tipo che può avere un valore o può essere vuoto.|
|[Elenchi](lists.md)|Descrive elenchi, ovvero la serie ordinata e non modificabile di elementi dello stesso tipo.|
|[Matrici](arrays.md)|Descrive matrici, che sono set ordinate di elementi modificabili dello stesso tipo che occupano un blocco di memoria contigue e sono di dimensioni fisse.|
|[Sequenze](sequences.md)|Descrive il tipo di sequenza che rappresenta una serie logica di valori. i singoli valori vengono calcolati solo se necessario.|
|[Record](records.md)|Descrive il tipo di record, una piccola funzione di aggregazione di valori denominati.|
|[Unioni discriminate](discriminated-unions.md)|Descrive il tipo di unione discriminata, un tipo i cui valori possono essere uno dei set di tipi possibili.|
|[Funzioni](functions/index.md)|Descrive i valori di funzione.|
|[Classi](classes.md)|Descrive il tipo di classe, un tipo di oggetto che corrisponde a un tipo di riferimento .NET. I tipi classe possono contenere membri, proprietà, le interfacce implementate e un tipo di base.|
|[Strutture](structures.md)|Viene descritto il `struct` tipo, tipo di oggetto che corrisponde a un tipo di valore .NET. Il `struct` tipo rappresenta in genere una piccola funzione di aggregazione dei dati.|
|[Interfacce](interfaces.md)|Descrive i tipi di interfaccia, ovvero i tipi che rappresentano un set di membri che fornire determinate funzionalità, ma che non contengono dati. Un tipo di interfaccia deve essere implementato da un tipo di oggetto per essere utile.|
|[Delegati](delegates.md)|Descrive il tipo delegato che rappresenta una funzione come oggetto.|
|[Enumerazioni](enumerations.md)|Descrive i tipi di enumerazione, i cui valori appartengano a un set di valori denominati.|
|[Attributi](attributes.md)|Descrive gli attributi, che vengono usati per specificare i metadati per un altro tipo.|
|[Tipi di eccezione](exception-handling/exception-types.md)|Vengono descritte le eccezioni, che specificano le informazioni sull'errore.|
