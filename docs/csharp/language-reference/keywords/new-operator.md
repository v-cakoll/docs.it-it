---
title: Operatore new - Riferimenti per C#
ms.custom: seodec18
ms.date: 03/15/2018
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: ce3d39c42dc35ca3038fc38edd9327e9b96fb20f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633426"
---
# <a name="new-operator-c-reference"></a>Operatore new (Riferimenti per C#)

Usato per creare oggetti e richiamare costruttori. Ad esempio:

```csharp
Class1 obj  = new Class1();
```

Viene usato anche per creare istanze di tipi anonimi:

```csharp
var query = from cust in customers
            select new { Name = cust.Name, Address = cust.PrimaryAddress };
```

L'operatore `new` viene usato anche per richiamare il costruttore senza parametri per i tipi di valore. Ad esempio:

```csharp
int i = new int();
```

Nell'istruzione precedente `i` viene inizializzato in `0`, ovvero il valore predefinito per il tipo `int`. L'istruzione ha lo stesso effetto dell'istruzione seguente:

```csharp
int i = 0;
```

Per un elenco completo dei valori predefiniti, vedere [Tabella dei valori predefiniti](default-values-table.md).

È utile ricordare che è errato dichiarare un costruttore senza parametri per uno [struct](struct.md) poiché ogni tipo di valore ha implicitamente un costruttore senza parametri pubblico. È possibile dichiarare costruttori con parametri su un tipo struct per impostarne i valori iniziali, ma questa operazione è necessaria solo se sono richiesti valori diversi da quello predefinito.

Sia gli oggetti di tipo valore come gli struct che gli oggetti di tipo riferimento come le classi vengono eliminati automaticamente, ma gli oggetti di tipo valore vengono eliminati quando viene eliminato il loro contesto contenitore, mentre gli oggetti di tipo riferimento vengono eliminati da Garbage Collector in un momento non specificato dopo la rimozione dell'ultimo riferimento a essi relativo. Per i tipi che contengono risorse come ad esempio gli handle di file o le connessioni di rete, è consigliabile adottare la pulitura deterministica per garantire che le risorse contenute vengano rilasciate nel più breve tempo possibile. Per altre informazioni, vedere [Istruzione using](using-statement.md).

Non è possibile sottoporre l'operatore `new` a overload.

Se l'operatore `new` non riesce ad allocare memoria, genererà l'eccezione <xref:System.OutOfMemoryException>.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono creati e inizializzati un oggetto `struct` e un oggetto classe usando l'operatore `new` e vengono quindi assegnati i valori. I valori predefiniti e assegnati sono visualizzati.

[!code-csharp[csrefKeywordsOperator#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#7)]

Si noti che nell'esempio il valore predefinito di una stringa è `null` e, pertanto, non viene visualizzato.

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../../language-reference/index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Parole chiave di C#](index.md)
- [Parole chiave per gli operatori](operator-keywords.md)
- [new](new.md)
- [Tipi anonimi](../../programming-guide/classes-and-structs/anonymous-types.md)
