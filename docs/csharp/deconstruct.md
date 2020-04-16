---
title: Decostruzione di tuple e altri tipi
description: Informazioni su come decostruire le tuple e altri tipi.
ms.technology: csharp-fundamentals
ms.date: 11/23/2017
ms.assetid: 0b0c4b0f-4a47-4f66-9b8e-f5c63b195960
ms.openlocfilehash: d238f6f520653befb1464377094b93e34dde0eca
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463132"
---
# <a name="deconstructing-tuples-and-other-types"></a>Decostruzione di tuple e altri tipi

Una tupla è un metodo semplice per recuperare più valori da una chiamata a un metodo. Tuttavia dopo aver recuperato la tupla è necessario gestirne i singoli elementi. Se eseguita un elemento alla volta, questa operazione può risultare molto laboriosa, come visualizzato nell'esempio seguente. Il metodo `QueryCityData` restituisce una tupla con 3 elementi e ogni elemento viene assegnato a una variabile in un'operazione separata.

[!code-csharp[WithoutDeconstruction](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple1.cs)]

Il recupero di più valori di campi e proprietà da un oggetto può essere altrettanto complesso: è necessario assegnare un valore di campo o proprietà a una variabile, un membro alla volta.

A partire da C# 7.0 è possibile recuperare più elementi da una tupla o recuperare più valori di campi, proprietà e valori calcolati da un oggetto in una singola operazione di *decostruzione*. Quando si decostruisce una tupla gli elementi corrispondenti vengono assegnati a singole variabili. Quando si decostruisce un oggetto si assegnano valori selezionati a singole variabili.

## <a name="deconstructing-a-tuple"></a>Decostruzione di una tupla

In C# è incluso il supporto per la decostruzione di tuple, che consente di decomprimere tutti gli elementi di una tupla in un'unica operazione. La sintassi generale per la decostruzione di una tupla è simile alla sintassi per la definizione della tupla: le variabili a cui va assegnato ogni elemento vengono racchiuse tra parentesi sul lato sinistro di un'istruzione di assegnazione. Ad esempio l'istruzione seguente assegna gli elementi di una tupla con 4 elementi a quattro variabili distinte:

```csharp
var (name, address, city, zip) = contact.GetAddressInfo();
```

Esistono tre modi per decostruire una tupla:

- È possibile dichiarare in modo esplicito il tipo di ogni campo all'interno di parentesi. Nell'esempio seguente viene usato questo approccio per decostruire la tupla con 3 elementi restituita dal metodo `QueryCityData`.

    [!code-csharp[Deconstruction-Explicit](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple2.cs#1)]

- È possibile usare la parola chiave `var` in modo che C# deduca il tipo di ogni variabile. Posizionare la parola chiave `var` all'esterno delle parentesi. Nell'esempio seguente viene usata l'inferenza del tipo questo approccio per decostruire la tupla con 3 elementi restituita dal metodo `QueryCityData`.

    [!code-csharp[Deconstruction-Infer](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple3.cs#1)]

    È anche possibile usare la parola chiave `var` individualmente con una o con tutte le dichiarazioni di variabili all'interno delle parentesi.

    [!code-csharp[Deconstruction-Infer-Some](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple4.cs#1)]

    Questo approccio è eccessivamente complesso e non è consigliato.

- Infine, è possibile decostruire la tupla in variabili che sono già state dichiarate.

    [!code-csharp[Deconstruction-Declared](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple5.cs#1)]

Si noti che non è possibile usare un tipo specifico all'esterno delle parentesi, anche se ogni campo nella tupla presenta lo stesso tipo. Questa operazione genera l'errore del compilatore CS8136 "Nel form di decostruzione 'var (...)' non è consentito un tipo specifico per 'var'".

Si noti anche che è necessario assegnare ogni elemento della tupla a una variabile. Se si omette un elemento, il compilatore genera l'errore CS8132: "Non è possibile decostruire una tupla di 'x' elementi in 'y' variabili".

Si noti che non è possibile combinare le dichiarazioni e le assegnazioni a variabili esistenti sul lato sinistro di una decostruzione. Questa operazione genera l'errore del compilatore CS8184: "Nella parte sinistra di una decostruzione non è possibile combinare dichiarazioni ed espressioni" quando i membri includono variabili esistenti e appena dichiarate.

## <a name="deconstructing-tuple-elements-with-discards"></a>Decostruzione degli elementi della tupla con variabili discard

Spesso quando si decostruisce una tupla si è interessati solo ai valori di alcuni elementi. A partire da C# 7.0 è possibile avvalersi del supporto in C# delle variabili *discard*, variabili di sola scrittura delle quali si è scelto di ignorare i valori. Una variabile discard è indicata da un carattere di sottolineatura ("\_") in un'assegnazione. È possibile rimuovere il numero di valori desiderato; tutti sono rappresentati dalla variabile discard singola `_`.

L'esempio seguente illustra l'uso delle tuple con le variabili discard. Il metodo `QueryCityDataForYears` restituisce una tupla con 6 elementi con il nome di una città, l'area della città, un anno, la popolazione della città per tale anno, un secondo anno e la popolazione della città per tale anno. L'esempio visualizza la variazione della popolazione tra questi due anni. Tra i dati resi disponibili dalla tupla non interessa l'area della città, mentre il nome della città e le due date sono già noti in fase di progettazione. Di conseguenza interessano soltanto i due valori di popolazione archiviati nella tupla, mentre gli altri valori possono essere gestiti come variabili discard.  

[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

## <a name="deconstructing-user-defined-types"></a>Decostruzione dei tipi definiti dall'utente

C# non offre il supporto predefinito per la decostruzione di tipi diversi da tuple. Tuttavia l'autore di una classe, uno struct o un'interfaccia può consentire la decostruzione di istanze del tipo implementando uno o più metodi `Deconstruct`. Il metodo restituisce un valore void e ogni valore da decostruire è indicato da un parametro [out](language-reference/keywords/out-parameter-modifier.md) nella firma del metodo. Ad esempio il seguente metodo `Deconstruct` di una classe `Person` restituisce il nome, il secondo nome e il cognome:

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#1)]

È quindi possibile decostruire un'istanza della classe `Person` denominata `p` con un'assegnazione simile alla seguente:

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#2)]

L'esempio che segue implementa l'overload del metodo `Deconstruct` per restituire varie combinazioni di proprietà di un oggetto `Person`. I singoli overload restituiscono:

- Un nome e un cognome.
- Un nome, un secondo nome e un cognome.
- Un nome, un cognome, un nome di città e un nome di stato.

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class2.cs)]

Poiché è possibile eseguire l'overload del metodo `Deconstruct` in modo da riflettere gruppi di dati estratti comunemente da un oggetto, è importante definire metodi `Deconstruct` con firme uniche e non ambigue. Più metodi `Deconstruct` che hanno lo stesso numero di parametri `out` o lo stesso numero e tipo di parametri `out` in un ordine diverso possono provocare confusione.

Il metodo `Deconstruct` con overload dell'esempio seguente visualizza una possibile causa di confusione. Il primo overload restituisce il nome, il secondo nome, il cognome e l'età di un oggetto `Person` in quest'ordine. Il secondo overload restituisce solo le informazioni del nome oltre al reddito annuale, ma i dati relativi a nome, secondo nome e cognome sono in un ordine diverso. In questo modo è più facile confondere l'ordine degli argomenti quando si esegue la decostruzione di un'istanza di `Person`.

[!code-csharp[Deconstruct-ambiguity](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-ambiguous.cs)]

## <a name="deconstructing-a-user-defined-type-with-discards"></a>Decostruzione di un tipo definito dall'utente con variabili discard

Come per le [tuple](#deconstructing-tuple-elements-with-discards), è possibile usare le variabili discard per ignorare elementi selezionati restituiti da un metodo `Deconstruct`. Ogni variabile discard è definita da una variabile denominata \_ e una singola operazione di decostruzione può includere diverse variabili discard.

L'esempio seguente esegue la decostruzione di un oggetto `Person` in quattro stringhe (nome, cognome, città e stato) ma rimuove il cognome e lo stato.

[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs#1)]

## <a name="deconstructing-a-user-defined-type-with-an-extension-method"></a>Decostruzione di un tipo definito dall'utente con un metodo di estensione

Anche un utente che non ha creato una classe, uno struct o un'interfaccia può eseguire la decostruzione di oggetti di questo tipo implementando uno o più `Deconstruct` [metodi di estensione](programming-guide/classes-and-structs/extension-methods.md) per restituire i valori che risultano di interesse.

L'esempio riportato di seguito illustra due metodi di estensione `Deconstruct` per la classe <xref:System.Reflection.PropertyInfo?displayProperty=nameWithType>. Il primo metodo restituisce un set di valori che indicano le caratteristiche della proprietà: il tipo, se è statica o di istanza, se è di sola lettura e se è indicizzata. Il secondo indica l'accessibilità della proprietà. Dato che l'accessibilità delle funzioni di accesso get e set può essere diversa, i valori booleani indicano se la proprietà ha funzioni di accesso get e set separate e in questo caso se tali funzioni presentano la stessa accessibilità. Se è presente solo una funzione di accesso o se le funzioni di accesso get e set hanno la stessa accessibilità, la variabile `access` indica l'accessibilità della proprietà nel suo complesso. In caso contrario l'accessibilità delle funzioni di accesso get e set è indicata dalle variabili `getAccess` e `setAccess`.

[!code-csharp[Extension-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-extension1.cs)]

## <a name="see-also"></a>Vedere anche

- [Variabili discard](discards.md)
- [Tuple](tuples.md)
