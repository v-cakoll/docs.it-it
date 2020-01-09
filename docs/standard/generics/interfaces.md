---
title: Interfacce generiche
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- generic interfaces [.NET Framework]
- equality comparisons [.NET Framework]
- generics [.NET Framework], interfaces
- ordering comparisons [.NET Framework]
ms.assetid: 88bf5b04-d371-4edb-ba38-01ec7cabaacf
ms.openlocfilehash: 704ada32d428c468d5b71a3f1390568ca586079e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708324"
---
# <a name="generic-interfaces"></a>Interfacce generiche
Questo argomento fornisce una panoramica delle interfacce generiche che forniscono funzionalità comuni a famiglie di tipi generici.  
  
## <a name="generic-interfaces"></a>Interfacce generiche  
 Le interfacce generiche forniscono controparti indipendenti dai tipi a interfacce non generiche per confronti di uguaglianza e ordinamento e per le funzionalità condivise da tipi di raccolta generici.  
  
> [!NOTE]
> A partire da .NET Framework 4, i parametri di tipo di diverse interfacce generiche vengono contrassegnati come covariante o controvariante, fornendo più flessibilità nell'assegnazione e nell'uso di tipi che implementano queste interfacce. Vedere [Covarianza e controvarianza](../../../docs/standard/generics/covariance-and-contravariance.md).  
  
### <a name="equality-and-ordering-comparisons"></a>Confronti di uguaglianza e ordinamento  
 Nello spazio dei nomi <xref:System> le interfacce generiche <xref:System.IComparable%601?displayProperty=nameWithType> e <xref:System.IEquatable%601?displayProperty=nameWithType>, analogamente alle relative controparti non generiche, definiscono rispettivamente i metodi per i confronti di ordinamento e quelli per i confronti di uguaglianza. I tipi implementano queste interfacce per consentire l'esecuzione di questi confronti.  
  
 Nello spazio dei nomi <xref:System.Collections.Generic> le interfacce generiche <xref:System.Collections.Generic.IComparer%601> e <xref:System.Collections.Generic.IEqualityComparer%601> consentono di definire un confronto di ordinamento o di uguaglianza per i tipi che non implementano l'interfaccia generica <xref:System.IComparable%601?displayProperty=nameWithType> o <xref:System.IEquatable%601?displayProperty=nameWithType> e forniscono un sistema per ridefinire tali relazioni nel caso di tipi che implementano l'interfaccia in questione. Queste interfacce sono usate da metodi e costruttori di molte delle classi di raccolta generiche. È ad esempio possibile passare un oggetto generico <xref:System.Collections.Generic.IComparer%601> al costruttore della classe <xref:System.Collections.Generic.SortedDictionary%602> per specificare un ordinamento per un tipo che non implementa un'interfaccia generica <xref:System.IComparable%601?displayProperty=nameWithType>. Sono presenti overload del metodo statico generico <xref:System.Array.Sort%2A?displayProperty=nameWithType> e del metodo di istanza <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> che consentono l'ordinamento di matrici ed elenchi mediante implementazioni generiche di <xref:System.Collections.Generic.IComparer%601>.  
  
 Le classi generiche <xref:System.Collections.Generic.Comparer%601> e <xref:System.Collections.Generic.EqualityComparer%601> forniscono classi base per le implementazioni delle interfacce generiche <xref:System.Collections.Generic.IComparer%601> e <xref:System.Collections.Generic.IEqualityComparer%601>, nonché confronti di ordinamento e uguaglianza predefiniti mediante le rispettive proprietà <xref:System.Collections.Generic.Comparer%601.Default%2A?displayProperty=nameWithType> e <xref:System.Collections.Generic.EqualityComparer%601.Default%2A?displayProperty=nameWithType>.  
  
### <a name="collection-functionality"></a>Funzionalità di raccolta  
 L'interfaccia generica <xref:System.Collections.Generic.ICollection%601> è l'interfaccia di base per i tipi di raccolta generici. Fornisce la funzionalità di base per l'aggiunta, la rimozione, la copia e l'enumerazione degli elementi. <xref:System.Collections.Generic.ICollection%601> eredita da interfacce <xref:System.Collections.Generic.IEnumerable%601> generiche e <xref:System.Collections.IEnumerable> non generiche.  
  
 L'interfaccia generica <xref:System.Collections.Generic.IList%601> estende l'interfaccia generica <xref:System.Collections.Generic.ICollection%601> con metodi per il recupero indicizzato.  
  
 L'interfaccia generica <xref:System.Collections.Generic.IDictionary%602> estende l'interfaccia generica <xref:System.Collections.Generic.ICollection%601> con metodi per il recupero con chiavi. Anche i tipi di dizionari generici della libreria di classi base .NET Framework implementano l'interfaccia <xref:System.Collections.IDictionary> non generica.  
  
 L'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601> fornisce una struttura di enumeratori generici. L'interfaccia generica <xref:System.Collections.Generic.IEnumerator%601> implementata dagli enumeratori generici eredita l'interfaccia <xref:System.Collections.IEnumerator> non generica e i membri <xref:System.Collections.IEnumerator.MoveNext%2A> e <xref:System.Collections.IEnumerator.Reset%2A>, che non dipendono dal parametro di tipo `T`, vengono visualizzati solo sull'interfaccia non generica. Di conseguenza, qualsiasi consumer dell'interfaccia non generica può usare anche l'interfaccia generica.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [Generics](../../../docs/standard/generics/index.md)
- [Raccolte generiche in .NET Framework](../../../docs/standard/generics/collections.md)
- [Delegati generici per la modifica di matrici ed elenchi](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)
- [Covarianza e controvarianza](../../../docs/standard/generics/covariance-and-contravariance.md)
