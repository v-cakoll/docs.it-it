---
title: Confronti e ordinamenti all'interno delle raccolte
ms.date: 04/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET Framework], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
ms.openlocfilehash: cb9dd3e8af570251b8bcd2e450e686ad69ab78c4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287978"
---
# <a name="comparisons-and-sorts-within-collections"></a>Confronti e ordinamenti all'interno delle raccolte

Le classi <xref:System.Collections> eseguono confronti in quasi tutti i processi di gestione delle raccolte, ricercando l'elemento da rimuovere o restituendo il valore di una coppia chiave-valore.

Le raccolte in genere usano un operatore di uguaglianza e/o un confronto di ordinamento. Vengono usati due costrutti per i confronti.

<a name="BKMK_Checkingforequality"></a>
## <a name="check-for-equality"></a>Verifica uguaglianza

I metodi come `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>e `Remove` usano un confronto di uguaglianza per gli elementi della raccolta. Se la raccolta è generica, gli elementi vengono confrontati per verificarne l'uguaglianza secondo le linee guida seguenti:

- Se il tipo T implementa l'interfaccia generica <xref:System.IEquatable%601> , il confronto di uguaglianza è il metodo <xref:System.IEquatable%601.Equals%2A> di tale interfaccia.

- Se il tipo T non implementa <xref:System.IEquatable%601>, viene usato <xref:System.Object.Equals%2A?displayProperty=nameWithType> .

Inoltre, alcuni overload del costruttore per le raccolte dizionario accettano un'implementazione di <xref:System.Collections.Generic.IEqualityComparer%601>, che viene usata per confrontare l'uguaglianza delle chiavi. Per un esempio, vedere il costruttore <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> .

<a name="BKMK_Determiningsortorder"></a>
## <a name="determine-sort-order"></a>Determinare il tipo di ordinamento

I metodi come `BinarySearch` e `Sort` usano un confronto di ordinamento per gli elementi della raccolta. È possibile eseguire il confronto tra gli elementi della raccolta o tra un elemento e un valore specificato. Per confrontare gli oggetti, esiste il concetto di `default comparer` e `explicit comparer`.

L'operatore di confronto predefinito si basa su almeno uno degli oggetti confrontati per implementare l'interfaccia **IComparable** . Si consiglia di implementare **IComparable** in tutte le classi che vengono usate come valori in una raccolta di elenchi o come chiavi in una raccolta di dizionari. Per una raccolta generica, il confronto di uguaglianza è determinato come segue:

- Se il tipo T implementa l'interfaccia generica <xref:System.IComparable%601?displayProperty=nameWithType> , l'operatore di confronto predefinito è il metodo <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> di tale interfaccia

- Se il tipo T implementa l'interfaccia non generica <xref:System.IComparable?displayProperty=nameWithType> , l'operatore di confronto predefinito è il metodo <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> di tale interfaccia.

- Se il tipo T non implementa alcuna interfaccia, non esiste alcun operatore di confronto predefinito ed è necessario fornire in modo esplicito un delegato di confronto o di confronto.

Per fornire i confronti espliciti, alcuni metodi accettano un'implementazione **IComparer** come parametro. Ad esempio, il metodo <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> accetta un'implementazione <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> .

L'impostazione cultura corrente del sistema può influenzare i confronti e gli ordinamenti all'interno di una raccolta. Per impostazione predefinita, i confronti e gli ordinamenti nelle classi **Collections** classi sono dipendenti dalle impostazioni cultura. Per ignorare l'impostazione cultura e quindi ottenere risultati coerenti di confronto e ordinamento, usare il <xref:System.Globalization.CultureInfo.InvariantCulture%2A> con gli overload dei membri che accettano un <xref:System.Globalization.CultureInfo>. Per altre informazioni, vedere [Performing Culture-Insensitive String Operations in Collections](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) e [Performing Culture-Insensitive String Operations in Arrays](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).

<a name="BKMK_Equalityandsortexample"></a>
## <a name="equality-and-sort-example"></a>Esempio di uguaglianza e ordinamento

Nel codice seguente viene illustrata un'implementazione di <xref:System.IEquatable%601> e <xref:System.IComparable%601> su un semplice oggetto business. Inoltre, quando l'oggetto viene memorizzato in un elenco e ordinato, la chiamata al metodo <xref:System.Collections.Generic.List%601.Sort> risulterà nell'uso dell'operatore di confronto predefinito per il tipo `Part` e il metodo <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> implementato usando un metodo anonimo.

[!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)]
[!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.IComparer>
- <xref:System.IEquatable%601>
- <xref:System.Collections.Generic.IComparer%601>
- <xref:System.IComparable>
- <xref:System.IComparable%601>
