---
title: Unità di misura (F#)
description: 'Informazioni su a virgola mobile come e i valori interi con segno in F # possono essere associate unità di misura, che sono in genere usata per indicare lunghezza, volume e massa.'
ms.date: 05/16/2016
ms.openlocfilehash: ad2193e25f3c0cee6e73cd529ab43d1e4b6b549b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187887"
---
# <a name="units-of-measure"></a>Unità di misura

Virgola mobile e i valori interi con segno in F # possono essere associate unità di misura, che sono in genere usata per indicare lunghezza, volume, massa, e così via. Con le quantità con unità, è consentire al compilatore di verificare che le relazioni aritmetiche dispongono di unità corretta, che consente di evitare gli errori di programmazione.

## <a name="syntax"></a>Sintassi

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Note

La sintassi precedente definisce *-nome dell'unità* come un'unità di misura. La parte facoltativa consente di definire una nuova misura in termini di unità definita in precedenza. Ad esempio, la riga seguente definisce la misura `cm` (centimetri).

```fsharp
[<Measure>] type cm
```

La riga seguente definisce la misura `ml` (millimetro) come un centimetro (`cm^3`).

```fsharp
[<Measure>] type ml = cm^3
```

Nella sintassi precedente *misura* è una formula che utilizza l'unità. Nelle formule che comportano l'unità, sono supportate le potenze di integrale (positivi e negativi), gli spazi tra le unità di indicano un prodotto di due unità, `*` indica un prodotto di unità, e `/` indica un quoziente di unità. Per un'unità reciproca, è possibile usare una potenza di numero intero negativo oppure un `/` che indica una separazione tra il numeratore e del denominatore di una formula di unità. Più unità nel denominatore devono essere racchiusi tra parentesi. Unità di misura separati da spazi dopo una `/` vengono interpretati come parte del denominatore, ma qualsiasi unità che segue un `*` vengono interpretati come parte del numeratore.

È possibile usare 1 nelle espressioni di unità, da solo per indicare una quantità senza, o insieme alle altre unità, ad esempio il numeratore. Ad esempio, viene scritto come le unità per una tariffa `1/s`, dove `s` indica i secondi. Parentesi non vengono utilizzate nelle formule di unità. Non si specifica le costanti di conversione numeriche nelle formule; unit Tuttavia, è possibile definire le costanti di conversione con unità separatamente e usati in calcoli unità controllata.

Le formule di unità con lo stesso significano possono essere scritti in vari modi equivalenti. Pertanto, il compilatore converte le formule di unità in un formato coerente, che converte potenze negative reciproci, raggruppando le unità in un singolo numeratore e del denominatore e dispone in ordine alfabetico le unità nel numeratore e del denominatore.

Ad esempio, le formule unit `kg m s^-2` e `m /s s * kg` vengono convertiti in `kg m/s^2`.

Si utilizzano unità di misura in espressioni a virgola mobile. L'uso di numeri a virgola mobile insieme a associate unità di misura aggiunge un ulteriore livello di indipendenza dai tipi e consente di evitare gli errori di mancata corrispondenza di unità che possono verificarsi nelle formule quando si usano tipizzazione debole numeri a virgola mobile. Se si scrivono mobile espressione punto che usa le unità, l'unità nell'espressione devono corrispondere.

È possibile annotare i valori letterali con una formula unit parentesi acute, come illustrato negli esempi seguenti.

```fsharp
1.0<cm>
55.0<miles/hour>
```

Non inserire uno spazio tra il numero e la parentesi angolare di; Tuttavia, è possibile includere un suffisso letterale, ad esempio `f`, come illustrato nell'esempio seguente.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Tale annotazione viene modificato il tipo del valore letterale dal relativo tipo primitivo (ad esempio `float`) a un tipo con dimensioni, ad esempio `float<cm>` o, in questo caso, `float<miles/hour>`. Un'annotazione di unità di `<1>` indica una quantità senza e il relativo tipo è equivalente al tipo primitivo senza un parametro dell'unità.

Il tipo di un'unità di misura è a virgola mobile o un tipo integrale con un'annotazione unità aggiuntiva, indicato tra parentesi quadre firmato. Di conseguenza, quando si scrive il tipo di una conversione da `g` (g) a `kg` (kg), si descrivono i tipi come indicato di seguito.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Unità di misura vengono usate per il controllo dell'unità in fase di compilazione ma non vengono mantenute nell'ambiente di runtime. Pertanto, non influiscono sulle prestazioni.

Unità di misura possono essere applicate a qualsiasi tipo, non solo tipi a virgola mobile; solo tipi a virgola mobile, firmato, tuttavia, i tipi integrali e tipi decimali supporto dimensionata quantità. Pertanto, è solo vantaggioso usare unità di misura aggregati che contengono questi tipi primitivi e tipi primitivi.

Nell'esempio seguente viene illustrato l'utilizzo di unità di misura.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

Esempio di codice seguente viene illustrato come convertire un numero a virgola mobile senza un valore a virgola mobile. Sufficiente moltiplicare per 1,0, applicare le dimensioni per la 1.0. È possibile astrarre questo in una funzione, ad esempio `degreesFahrenheit`.

Inoltre, quando si passano valori con dimensioni per le funzioni che si aspettano di numeri a virgola mobile senza dimensioni, è necessario annullare questa operazione le unità o eseguire il cast `float` utilizzando il `float` operatore. In questo esempio, si divide per `1.0<degC>` per gli argomenti `printf` perché `printf` prevede quantità senza dimensioni.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

La sessione di esempio seguente mostra l'output da e input per questo codice.

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Utilizzo unità di misura generici

È possibile scrivere funzioni generiche che operano sui dati che sono associata un'unità di misura. Eseguire questa operazione specificando un tipo di insieme a un'unità generica come parametro di tipo, come illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a>Creazione di tipi di aggregazione con unità di misura generici

Il codice seguente viene illustrato come creare un tipo di aggregazione che è costituito da singoli valori a virgola mobile con unità di misura generici. In questo modo un solo tipo da creare che funziona con un'ampia gamma di unità. Unità di misura generici conservano anche, indipendenza dai tipi garantendo che un tipo generico che ha un set di unità è un tipo diverso dallo stesso tipo generico con un set diverso di unità. Alla base di questa tecnica è che il `Measure` attributo può essere applicato al parametro di tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a>Unità in fase di esecuzione

Unità di misura sono usate per il controllo dei tipi statici. Se i valori a virgola mobile vengono compilati, vengono eliminate le unità di misura, in modo che le unità vengono perse in fase di esecuzione. Pertanto, qualsiasi tentativo di implementare funzionalità che dipende dal controllo delle unità in fase di esecuzione non è possibile. Ad esempio possibile implementare un `ToString` funzione per stampare le unità non è possibile.

## <a name="conversions"></a>Conversioni

Per convertire un tipo che dispone di unità (ad esempio, `float<'u>`) a un tipo che non dispone di unità, è possibile usare la funzione di conversione standard. Ad esempio, è possibile usare `float` da convertire in un `float` valore che non dispone di unità, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Per convertire un valore senza unità su un valore che dispone di unità, è possibile moltiplicare per valore 1 o 1.0 annotato con le unità appropriate. Tuttavia, per la scrittura di livelli di interoperabilità, esistono anche alcune funzioni esplicite che è possibile utilizzare per convertire i valori senza unità per i valori con le unità. Si tratta nel [LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) modulo. Ad esempio, per eseguire la conversione da un valore `float` a un `float<cm>`, usare [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a>Unità di misura nella raccolta di base F #

È disponibile in una libreria unit di `FSharp.Data.UnitSystems.SI` dello spazio dei nomi. Include le unità di sistema internazionale di misura in entrambi i form di simboli (, ad esempio `m` contatore) nel `UnitSymbols` sub-spazio dei nomi e il relativo nome completo (, ad esempio `meter` contatore) nel `UnitNames` spazio dei nomi secondario.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
