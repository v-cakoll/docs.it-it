---
title: Unità di misura (F#)
description: 'A virgola mobile come informazioni e i valori interi con segno in F # è possono associare le unità di misura, che sono in genere usate per indicare lunghezza, volume e massa.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 336a1e04426fb39f5ceb98e06a06cd7eadc36e85
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="units-of-measure"></a>Unità di misura

A virgola mobile e interi con segno in F # possono essere associate unità di misura, che sono in genere usata per indicare la lunghezza, volume, massa, e così via. Con quantità di unità, consente al compilatore di verificare che le relazioni aritmetiche dispongano di unità corretta, che consente di evitare errori di programmazione.


## <a name="syntax"></a>Sintassi

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Note
Definisce la sintassi precedente *-nome dell'unità* come un'unità di misura. La parte facoltativa viene utilizzata per definire una nuova misura in termini di unità definita in precedenza. Ad esempio, la riga seguente definisce la misura `cm` (centimetri).

```fsharp
[<Measure>] type cm
```

La riga seguente definisce la misura `ml` (millimetro) come un centimetro (`cm^3`).

```fsharp
[<Measure>] type ml = cm^3
```

Nella sintassi precedente, *misura* è una formula che vengono utilizzate unità. Nelle formule che comportano l'unità, sono supportate le potenze integrali (positive e negative), gli spazi tra le unità indicano un prodotto di due unità, `*` indica un prodotto di unità, e `/` indica un quoziente di unità. Per un'unità reciproca, è possibile utilizzare una potenza intera negativa o `/` che indica una separazione tra il numeratore e un denominatore di una formula di unità. Più unità nel denominatore devono essere racchiusi tra parentesi. Unità di misura separati da spazi dopo un `/` vengono interpretati come parte del denominatore, ma qualsiasi unità che segue un `*` vengono interpretati come parte del numeratore.

È possibile utilizzare 1 nelle espressioni di unità, da solo per indicare una quantità, senza o con altre unità, ad esempio nel numeratore. Ad esempio, le unità per una velocità verrebbero scritto come `1/s`, dove `s` indica i secondi. Parentesi non vengono utilizzate nelle formule di unità. Non si specifica le costanti di conversione numerica nelle formule di unità; Tuttavia, è possibile definire le costanti di conversione con unità separatamente e utilizzarle nei calcoli unità controllata.

Le formule di unità con lo stesso significato possono essere scritti in diversi modi equivalenti. Pertanto, il compilatore converte le formule di unità in un formato coerente, che converte potenze negative in reciproci, unità di gruppi in un unico numeratore e un denominatore e dispone in ordine alfabetico le unità in cui il numeratore e il denominatore.

Ad esempio, le formule di unità `kg m s^-2` e `m /s s * kg` vengono convertiti in `kg m/s^2`.

Si utilizzano unità di misura in espressioni a virgola mobile. Utilizzando i numeri a virgola mobile insieme associate unità di misura consente di aggiungere un altro livello dell'indipendenza dai tipi e aiuta a evitare gli errori di mancata corrispondenza di unità che possono verificarsi nelle formule, quando si utilizzano tipizzazione numeri a virgola mobile. Se si scrivono mobile espressione punto che utilizza le unità, le unità nell'espressione devono corrispondere.

È possibile annotare i valori letterali con una formula di unità tra parentesi quadre, come illustrato negli esempi seguenti.

```fsharp
1.0<cm>
55.0<miles/hour>
```

Non inserire uno spazio tra il numero e la parentesi angolare; Tuttavia, è possibile includere un suffisso letterale, ad esempio `f`, come nell'esempio seguente.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Tale annotazione modifica il tipo del valore letterale di tipo primitivo (ad esempio `float`) a un tipo con dimensioni, ad esempio `float<cm>` o, in questo caso, `float<miles/hour>`. Un'annotazione di unità di `<1>` indica una quantità senza e il relativo tipo è equivalente al tipo primitivo senza un parametro di unità.

Il tipo di un'unità di misura è una virgola mobile o un tipo integrale con un'annotazione di unità aggiuntive, indicata tra parentesi quadre firmato. Pertanto, quando si scrive il tipo di una conversione da `g` (g) per `kg` (kg), si descrivono i tipi, come indicato di seguito.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Unità di misura vengono utilizzate per il controllo dell'unità in fase di compilazione, ma non vengono rese persistenti nell'ambiente di runtime. Pertanto, non influiscono sulle prestazioni.

Unità di misura può essere applicata a qualsiasi tipo, non solo tipi a virgola mobile; Tuttavia, solo tipi a virgola mobile, firma tipi integrali e tipi decimali supporto dimensionata quantità. Pertanto, è solo logico utilizzare unità di misura su tipi primitivi e le aggregazioni che contengono questi tipi primitivi.

Nell'esempio seguente viene illustrato l'utilizzo di unità di misura.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
Esempio di codice seguente viene illustrato come convertire un numero a virgola mobile senza un valore a virgola mobile. Sufficiente moltiplicare per 1,0, applicare le dimensioni di 1.0. È possibile astrarre questo in una funzione come `degreesFahrenheit`.

Inoltre, quando si passano valori con dimensioni a funzioni che prevedono numeri a virgola mobile senza dimensioni, è necessario eliminare le unità o eseguire il cast a `float` utilizzando il `float` operatore. In questo esempio, si divide per `1.0<degC>` per gli argomenti di `printf` perché `printf` prevede quantità senza dimensioni.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

La sessione di esempio seguente viene illustrato l'output da e gli input per questo codice.

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Utilizzo di unità generiche
È possibile scrivere funzioni generiche che operano sui dati che sono associata un'unità di misura. Eseguire questa operazione specificando un tipo di insieme a un'unità generico come un parametro di tipo, come illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a>Creazione di tipi di aggregazione con unità generiche
Il codice seguente viene illustrato come creare un tipo di aggregazione che è costituito da singoli valori a virgola mobile con unità generiche. In questo modo un unico tipo da creare che funziona con un'ampia gamma di unità. Inoltre, le unità generiche mantengono indipendenza dai tipi assicurando che un tipo generico che ha un set di unità è un tipo diverso rispetto al tipo generico stesso con un set diverso di unità. Questa tecnica è che il `Measure` attributo può essere applicato al parametro di tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a>Unità in fase di esecuzione
Unità di misura vengono utilizzate per il controllo dei tipi statici. Se i valori a virgola mobile vengono compilati, vengono eliminate le unità di misura, quindi le unità vengono perse in fase di esecuzione. Pertanto, qualsiasi tentativo di implementare funzionalità che dipende dalla verifica le unità in fase di esecuzione non è possibile. Ad esempio possibile implementare un `ToString` funzione per stampare le unità non è possibile.


## <a name="conversions"></a>Conversioni
Per convertire un tipo che dispone di unità (ad esempio, `float<'u>`) a un tipo che non dispone di unità, è possibile utilizzare la funzione di conversione standard. Ad esempio, è possibile utilizzare `float` per convertire un `float` valore che non dispone di unità, come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Per convertire un valore senza unità in un valore che dispone di unità, è possibile moltiplicare per un valore di 1 o 1,0 annotato con le unità appropriate. Tuttavia, per la scrittura di livelli di interoperabilità, esistono anche alcune funzioni esplicite che è possibile utilizzare per convertire i valori senza unità in valori con unità di misura. Si tratta nel [LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) modulo. Ad esempio, per eseguire la conversione da un valore `float` per un `float<cm>`, utilizzare [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), come illustrato nel codice seguente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a>Unità di misura in F # Power Pack
Una raccolta di unità è disponibile in PowerPacks F #. La libreria di unità include unità SI e costanti fisiche.


## <a name="see-also"></a>Vedere anche
[Riferimenti per il linguaggio F#](index.md)
