---
title: Unità di misura
description: Informazioni sul modo in cui i valori a virgola mobile e Signed Integer in F# possono avere unità di misura associate, che in genere vengono usate per indicare la lunghezza, il volume e la massa.
ms.date: 05/16/2016
ms.openlocfilehash: f97eac9984f934c55aff8cf9f287afbc3aa098f3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630154"
---
# <a name="units-of-measure"></a>Unità di misura

I valori a virgola mobile e F# Signed Integer in possono avere unità di misura associate, che in genere vengono usate per indicare lunghezza, volume, massa e così via. Utilizzando quantità con unità, è possibile abilitare il compilatore per verificare che le relazioni aritmetiche dispongano delle unità corrette, evitando così errori di programmazione.

## <a name="syntax"></a>Sintassi

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a>Note

La sintassi precedente definisce *nome-unità* come unità di misura. La parte facoltativa viene usata per definire una nuova misura in termini di unità definite in precedenza. La riga seguente, ad esempio, definisce la `cm` misura (centimetri).

```fsharp
[<Measure>] type cm
```

La riga seguente definisce la misura `ml` (millilitro) come centimetro cubico (`cm^3`).

```fsharp
[<Measure>] type ml = cm^3
```

Nella sintassi precedente, *Measure* è una formula che include unità. Nelle formule che coinvolgono unità, i poteri integrali sono supportati (positivi e negativi), spazi tra unità indicano un prodotto delle due unità, `*` indica anche un prodotto di unità e `/` indica un quoziente di unità. Per un'unità reciproca, è possibile usare una potenza di tipo integer `/` negativa o un che indica una separazione tra il numeratore e il denominatore di una formula di unità. Più unità nel denominatore devono essere racchiuse tra parentesi. Le unità separate da spazi dopo `/` un oggetto vengono interpretate come parte del denominatore, ma tutte le `*` unità successive a vengono interpretate come parte del numeratore.

È possibile usare 1 nelle espressioni Unit, solo per indicare una quantità senza dimensione o insieme ad altre unità, ad esempio nel numeratore. Ad esempio, le unità per una frequenza verranno scritte come `1/s`, dove `s` indica i secondi. Le parentesi non vengono utilizzate nelle formule di unità. Nelle formule di unità non vengono specificate costanti di conversione numerica. Tuttavia, è possibile definire le costanti di conversione con le unità separatamente e usarle nei calcoli controllati dall'unità.

Le formule Unit che comportano la stessa operazione possono essere scritte in diversi modi equivalenti. Pertanto, il compilatore converte le formule di unità in un formato coerente, che converte i poteri negativi in reciproci, raggruppa le unità in un numeratore singolo e un denominatore e dispone le unità nel numeratore e nel denominatore.

Ad esempio, le formule `kg m s^-2` unit e `m /s s * kg` sono entrambe convertite in. `kg m/s^2`

Le unità di misura vengono usate nelle espressioni a virgola mobile. L'utilizzo di numeri a virgola mobile insieme a unità di misura associate aggiunge un altro livello di indipendenza dai tipi e consente di evitare gli errori di mancata corrispondenza tra le unità che possono verificarsi nelle formule quando si utilizzano numeri a virgola mobile con tipizzazione debole. Se si scrive un'espressione a virgola mobile che usa unità, le unità nell'espressione devono corrispondere.

È possibile annotare i valori letterali con una formula di unità tra parentesi acute, come illustrato negli esempi seguenti.

```fsharp
1.0<cm>
55.0<miles/hour>
```

Non viene inserito uno spazio tra il numero e la parentesi angolare; Tuttavia, è possibile includere un suffisso letterale `f`, ad esempio, come nell'esempio seguente.

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

Tale annotazione consente di modificare il tipo del valore letterale dal tipo primitivo (ad esempio `float`) a un tipo dimensionato, `float<cm>` ad esempio o `float<miles/hour>`, in questo caso. Un'annotazione `<1>` unità di indica una quantità senza dimensione e il relativo tipo è equivalente al tipo primitivo senza un parametro di unità.

Il tipo di unità di misura è un tipo a virgola mobile o integrale con segno insieme a un'annotazione unità aggiuntiva, indicata tra parentesi quadre. Pertanto, quando si scrive il tipo di una conversione da `g` (grammi) a `kg` (chilogrammi), si descrivono i tipi come segue.

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

Le unità di misura vengono utilizzate per il controllo delle unità in fase di compilazione ma non vengono rese permanente nell'ambiente di Runtime. Pertanto, non influiscono sulle prestazioni.

Le unità di misura possono essere applicate a qualsiasi tipo, non solo ai tipi a virgola mobile. Tuttavia, solo i tipi a virgola mobile, i tipi integrali con segno e i tipi decimali supportano le quantità dimensionate. Pertanto, è opportuno usare unità di misura sui tipi primitivi e sulle aggregazioni che contengono questi tipi primitivi.

Nell'esempio seguente viene illustrato l'utilizzo di unità di misura.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]

Nell'esempio di codice riportato di seguito viene illustrato come eseguire la conversione da un numero a virgola mobile non dimensionato a un valore a virgola mobile a dimensione. È sufficiente moltiplicare per 1,0, applicando le dimensioni al 1,0. È possibile astrarre questo oggetto in una `degreesFahrenheit`funzione come.

Inoltre, quando si passano valori dimensionati a funzioni che prevedono numeri a virgola mobile senza dimensione, è necessario annullare le unità `float` o eseguire il `float` cast a utilizzando l'operatore. In questo esempio si divide `1.0<degC>` per per gli argomenti in `printf` perché `printf` prevede quantità di dimensioni.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

Nella sessione di esempio seguente vengono mostrati gli output di e gli input di questo codice.

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a>Uso di unità generiche

È possibile scrivere funzioni generiche che operano su dati a cui è associata un'unità di misura. A tale scopo, specificare un tipo insieme a un'unità generica come parametro di tipo, come illustrato nell'esempio di codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]

## <a name="creating-aggregate-types-with-generic-units"></a>Creazione di tipi aggregati con unità generiche

Nel codice seguente viene illustrato come creare un tipo di aggregazione costituito da singoli valori a virgola mobile con unità generiche. In questo modo è possibile creare un singolo tipo che funzioni con un'ampia gamma di unità. Inoltre, le unità generiche conservano l'indipendenza dai tipi assicurando che un tipo generico con un set di unità sia un tipo diverso da quello dello stesso tipo generico con un set di unità diverso. La base di questa tecnica è che l' `Measure` attributo può essere applicato al parametro di tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]

## <a name="units-at-runtime"></a>Unità in fase di esecuzione

Le unità di misura vengono usate per il controllo dei tipi statici. Quando vengono compilati i valori a virgola mobile, le unità di misura vengono eliminate, quindi le unità vengono perse in fase di esecuzione. Pertanto, qualsiasi tentativo di implementare le funzionalità che dipendono dal controllo delle unità in fase di esecuzione non è possibile. Ad esempio, l'implementazione `ToString` di una funzione per stampare le unità non è possibile.

## <a name="conversions"></a>Conversioni

Per convertire un tipo che dispone di unità (ad esempio `float<'u>`,) in un tipo che non dispone di unità, è possibile utilizzare la funzione di conversione standard. Ad esempio, è possibile usare `float` per eseguire la conversione `float` in un valore che non dispone di unità, come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

Per convertire un valore senza unità in un valore con unità, è possibile moltiplicare per un valore 1 o 1,0 annotato con le unità appropriate. Tuttavia, per la scrittura di livelli di interoperabilità, sono disponibili anche alcune funzioni esplicite che è possibile usare per convertire i valori senza unità in valori con unità. Si trovano nel modulo [Microsoft. FSharp. Core. LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) . Ad esempio, per eseguire la conversione da un `float` elemento a `float<cm>`un oggetto, usare [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), come illustrato nel codice seguente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]

## <a name="units-of-measure-in-the-f-core-library"></a>Unità di misura nella libreria F# principale

Una libreria di unità è disponibile nello `FSharp.Data.UnitSystems.SI` spazio dei nomi. Sono incluse le unità si sia nella forma dei simboli ( `m` ad esempio per il `UnitSymbols` contatore) nello spazio dei nomi, sia nel nome completo `meter` (ad esempio per il `UnitNames` contatore) nello spazio dei nomi secondario.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio F#](index.md)
