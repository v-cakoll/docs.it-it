---
title: Tipi F#
description: 'Informazioni sui tipi utilizzati in F # e come tipi F # sono denominati e descritto.'
ms.date: 05/16/2016
ms.openlocfilehash: bdbb89dc751970ac31fe102df009f0bff6388e52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565589"
---
# <a name="f-types"></a>Tipi F#

In questo argomento vengono descritti i tipi utilizzati in F # e come tipi F # sono denominati e descritto.


## <a name="summary-of-f-types"></a>Riepilogo dei tipi F #
Alcuni tipi sono considerati *tipi primitivi*, ad esempio il tipo booleano `bool` e tipi integrali e a virgola mobile di varie dimensioni, che includono i tipi di caratteri e i byte. Questi tipi sono descritti [tipi primitivi](primitive-types.md).

Altri tipi che sono integrate nel linguaggio includono tuple, elenchi, matrici, sequenze, record, unioni discriminate. Se si dispone di esperienza con altri linguaggi .NET e formazione F #, è consigliabile leggere gli argomenti per ognuno di questi tipi. In sono inclusi collegamenti a ulteriori informazioni su questi tipi di [argomenti correlati](https://msdn.microsoft.com/library/#rel) sezione di questo argomento. F #-tipi specifici supportano gli stili di programmazione comuni ai linguaggi di programmazione funzionale. Molti di questi tipi sono associati moduli nella libreria F # che supportano operazioni frequenti in questi tipi.

Il tipo di una funzione include informazioni sui tipi di parametro e tipo restituito.

.NET Framework è l'origine di tipi di oggetto, tipi interfaccia, tipi delegati e ad altri utenti. Come in qualsiasi altro linguaggio .NET, è possibile definire i tipi di oggetto.

Inoltre, codice F # possibile definire gli alias, ovvero sono denominati *abbreviazioni di tipo*, che sono nomi alternativi per i tipi. È possibile utilizzare le abbreviazioni di tipo quando il tipo potrebbe cambiare in futuro e si desidera evitare di modificare il codice che dipende dal tipo. In alternativa, è possibile utilizzare un'abbreviazione di tipo come un nome descrittivo per un tipo che può rendere più facile da leggere e comprendere codice.

F # fornisce tipi di raccolta utile progettate con la programmazione funzionale in considerazione. Utilizzare questi tipi di raccolta consente di scrivere codice che è più funziona in stile. Per ulteriori informazioni, vedere [tipi di raccolta F #](fsharp-collection-types.md).


## <a name="syntax-for-types"></a>Sintassi per i tipi
Nel codice F #, spesso è necessario scrivere i nomi dei tipi. Ogni tipo ha un formato sintattico e utilizzare questi moduli in annotazioni di tipo, le dichiarazioni di metodo astratto, le dichiarazioni di delegato, le firme e altri costrutti sintattici. Quando si dichiara un nuovo costrutto di programma l'interprete, l'interprete stampa il nome del costrutto e la sintassi per il relativo tipo. Questa sintassi potrebbe essere semplicemente un identificatore per un tipo definito dall'utente o un identificatore incorporato, ad esempio `int` o `string`, ma per i tipi più complessi, la sintassi è più complessa.

La tabella seguente illustra gli aspetti della sintassi di tipo per i tipi F #.



|Tipo|Sintassi di tipo|Esempi|
|----|-----------|--------|
|tipo primitivo|*type-name*|`int`<br /><br />`float`<br /><br />`string`|
|tipo di aggregazione (classe, struttura, unione, record, enumerazione e così via)|*type-name*|`System.DateTime`<br /><br />`Color`|
|abbreviazione di tipo|*nome abbreviazione di tipo*|`bigint`|
|nome completo del tipo|*Namespaces.Type-nome*<br /><br />oppure<br /><br />*Modules.Type-nome*<br /><br />oppure<br /><br />*Namespaces.Modules.Type-nome*|`System.IO.StreamWriter`|
|array|*nome del tipo*[] o<br /><br />*nome del tipo* matrice|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|matrice bidimensionale|*nome del tipo*[,]|`int[,]`<br /><br />`float[,]`|
|Matrice tridimensionale|*nome del tipo*[,]|`float[,,]`|
|tuple|*tipo nome1* &#42; *tipo name2* ...|Ad esempio, `(1,'b',3)` è di tipo `int * char * int`|
|tipo generico|*parametro di tipo* *nome di tipo generico*<br /><br />oppure<br /><br />*nome di tipo generico*&lt;*elenco di parametri di tipo*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|(un tipo generico che ha fornito un argomento di tipo specifico) di tipo costruito|*argomento di tipo* *nome di tipo generico*<br /><br />oppure<br /><br />*nome di tipo generico*&lt;*elenco di argomenti tipo*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|tipo di funzione che dispone di un parametro singolo|*parametro-tipo1*  - &gt; *tipo restituito*|Una funzione che accetta un `int` e restituisce un `string` è di tipo `int -> string`|
|tipo di funzione che dispone di più parametri|*parametro-tipo1*  - &gt; *parametro type2*  - &gt; ... -&gt; *tipo restituito*|Una funzione che accetta un `int` e un `float` e restituisce un `string` è di tipo `int -> float -> string`|
|funzione di ordine superiore come parametro|(*-tipo di funzione*)|`List.map` è di tipo `('a -> 'b) -> 'a list -> 'b list`|
|delegato|delegato di *-tipo di funzione*|`delegate of unit -> int`|
|tipo flessibile|#*nome del tipo*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Argomenti correlati


|Argomento|Descrizione|
|-----|-----------|
|[Tipi primitivi](primitive-types.md)|Descrive i tipi semplici incorporati, ad esempio tipi integrali, il tipo booleano e i tipi di carattere.|
|[Tipo di unità](unit-type.md)|Viene descritto il `unit` tipo, un tipo che ha un valore e che è indicato da (); equivalente alla `void` in c# e `Nothing` in Visual Basic.|
|[Tuple](tuples.md)|Descrive il tipo di tupla, un tipo che è costituito da valori associati di qualsiasi tipo raggruppati in coppie, Triple, quattro elementi e così via.|
|[Opzioni](options.md)|Descrive il tipo di opzione, un tipo che può avere un valore o essere vuoto.|
|[Elenchi](lists.md)|Vengono descritti gli elenchi, che sono una serie ordinata e non modificabile di elementi tutti dello stesso tipo.|
|[Array](arrays.md)|Descrive le matrici, che sono ordinati in set di elementi modificabili dello stesso tipo che occupano un blocco contiguo di memoria e hanno dimensione fissa.|
|[Sequenze](sequences.md)|Descrive il tipo di sequenza, che rappresenta una serie logica di valori. i singoli valori vengono calcolati solo se necessario.|
|[Record](records.md)|Descrive il tipo di record, una piccola aggregazione di valori denominati.|
|[Unioni discriminate](discriminated-unions.md)|Descrive il tipo di unione discriminato, un tipo i cui valori possono essere uno di un set di possibili tipi.|
|[Funzioni](functions/index.md)|Vengono descritti i valori di funzione.|
|[Classi](classes.md)|Descrive il tipo di classe, un tipo di oggetto che corrisponde a un tipo di riferimento di .NET. Tipi di classe possono contenere membri, proprietà, le interfacce implementate e un tipo di base.|
|[Strutture](structures.md)|Viene descritto il `struct` tipo, tipo di oggetto che corrisponde a un tipo di valore .NET. Il `struct` tipo rappresenta in genere una piccola aggregazione di dati.|
|[Interfacce](interfaces.md)|Descrive i tipi di interfaccia, che sono tipi che rappresentano un set di membri che forniscono determinate funzionalità, ma che non contengono dati. Un tipo di interfaccia deve essere implementato da un tipo di oggetto per essere utile.|
|[Delegati](delegates.md)|Descrive il tipo di delegato, che rappresenta una funzione come oggetto.|
|[Enumerazioni](enumerations.md)|Descrive i tipi di enumerazione, i cui valori appartengono a un set di valori denominati.|
|[Attributi](attributes.md)|Vengono descritti attributi, che consentono di specificare i metadati per un altro tipo.|
|[Tipi di eccezione](exception-handling/exception-types.md)|Descrive le eccezioni, che specificano le informazioni di errore.|
