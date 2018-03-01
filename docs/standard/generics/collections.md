---
title: Collection generiche in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], collections
- generic collections [.NET Framework]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7e7d11446c14cffbef1e5cade5f082874187636
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="generic-collections-in-the-net-framework"></a>Collection generiche in .NET Framework
Questo argomento offre una panoramica delle classi Collection generiche e di altri tipi generici in .NET Framework.  
  
## <a name="generic-collections-in-the-net-framework"></a>Raccolte generiche in .NET Framework  
 La libreria di classi .NET Framework fornisce una serie di classi di raccolte generiche negli spazi dei nomi <xref:System.Collections.Generic> e <xref:System.Collections.ObjectModel>. Per altre informazioni su queste classi, vedere [Tipi di raccolte comunemente usate](../../../docs/standard/collections/commonly-used-collection-types.md).  
  
### <a name="systemcollectionsgeneric"></a>System.Collections.Generic  
 Diversi tipi di raccolta generici sono analoghi diretti di tipi non generici. <xref:System.Collections.Generic.Dictionary%602> è una versione generica di <xref:System.Collections.Hashtable>. Usa la struttura generica <xref:System.Collections.Generic.KeyValuePair%602> per l'enumerazione invece di <xref:System.Collections.DictionaryEntry>.  
  
 <xref:System.Collections.Generic.List%601> è una versione generica di <xref:System.Collections.ArrayList>. Esistono classi <xref:System.Collections.Generic.Queue%601> e <xref:System.Collections.Generic.Stack%601> generiche che corrispondono alle versioni non generiche.  
  
 Esistono versioni generiche e non generiche di <xref:System.Collections.Generic.SortedList%602>. Entrambe le versioni sono ibridi di un dizionario e di un elenco. La classe generica <xref:System.Collections.Generic.SortedDictionary%602> è un dizionario vero e proprio e non ha una controparte non generica.  
  
 La classe generica <xref:System.Collections.Generic.LinkedList%601> è un vero elenco collegato. Non ha una controparte non generica.  
  
### <a name="systemcollectionsobjectmodel"></a>System.Collections.ObjectModel  
 La classe generica <xref:System.Collections.ObjectModel.Collection%601> fornisce una classe base da cui derivare i propri tipi di raccolta generici. La classe <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> consente di creare facilmente una raccolta di sola lettura dai tipi che implementano l'interfaccia generica <xref:System.Collections.Generic.IList%601>. La classe generica <xref:System.Collections.ObjectModel.KeyedCollection%602> consente di archiviare oggetti contenenti le relative chiavi.  
  
## <a name="other-generic-types"></a>Altri tipi generici  
 La struttura generica <xref:System.Nullable%601> consente di usare tipi di valore come se potessero essere impostati su `null`. Può risultare utile quando si usano query di database, dove possono mancare campi che contengono tipi di valore. Il parametro di un tipo generico può essere qualsiasi tipo di valore.  
  
> [!NOTE]
>  In C# non è necessario usare <xref:System.Nullable%601> in modo esplicito perché questo linguaggio dispone della sintassi per i tipi nullable.  
  
 La struttura generica <xref:System.ArraySegment%601> consente di delimitare un intervallo di elementi in una matrice unidimensionale in base zero di qualsiasi tipo. Il parametro di tipo generico è il tipo degli elementi della matrice.  
  
 Con il delegato generico <xref:System.EventHandler%601> non è più necessario dichiarare un tipo di delegato per gestire gli eventi, se l'evento segue il modello di gestione degli eventi usato da [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Si supponga, ad esempio, di aver creato una classe `MyEventArgs`, derivata da <xref:System.EventArgs>, in cui includere i dati dell'evento. È quindi possibile dichiarare l'evento come indicato di seguito:  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Collections.Generic?displayProperty=nameWithType>  
 <xref:System.Collections.ObjectModel?displayProperty=nameWithType>  
 [Generics](../../../docs/standard/generics/index.md)  
 [Delegati generici per la modifica di matrici ed elenchi](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)  
 [Interfacce generiche](../../../docs/standard/generics/interfaces.md)
