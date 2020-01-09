---
title: Delegati generici per la modifica di matrici ed elenchi
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- delegates [.NET Framework], generic delegates
- chaining delegates
- arrays [.NET Framework], generic delegates
- generic delegates [.NET Framework]
- lists [.NET Framework], generic delegates
- generics [.NET Framework], delegates
ms.assetid: 416be383-cc61-4102-9b1b-88b51adb963e
ms.openlocfilehash: baf8497289ee71c2dbdc544607212de90928289c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708384"
---
# <a name="generic-delegates-for-manipulating-arrays-and-lists"></a>Delegati generici per la modifica di matrici ed elenchi
Questo argomento offre una panoramica dei delegati generici per conversioni, predicati di ricerca e azioni da eseguire sugli elementi di una matrice o di una raccolta.  
  
## <a name="generic-delegates-for-manipulating-arrays-and-lists"></a>Delegati generici per la modifica di matrici ed elenchi  
 Il delegato generico <xref:System.Action%601> rappresenta un metodo che esegue una determinata azione su un elemento del tipo specificato. È possibile creare un metodo che esegua l'azione desiderata sull'elemento, creare un'istanza del delegato <xref:System.Action%601> per rappresentare il metodo e quindi passare la matrice e il delegato al metodo generico statico <xref:System.Array.ForEach%2A?displayProperty=nameWithType>, che viene chiamato per ogni elemento della matrice.  
  
 La classe generica <xref:System.Collections.Generic.List%601> fornisce inoltre un metodo <xref:System.Collections.Generic.List%601.ForEach%2A> che usa il delegato <xref:System.Action%601>. Questo metodo non è generico.  
  
> [!NOTE]
> Quanto indicato sopra fornisce uno spunto interessante riguardo ai metodi e ai tipi generici. Il metodo <xref:System.Array.ForEach%2A?displayProperty=nameWithType> deve essere statico (`Shared` in Visual Basic) e generico perché <xref:System.Array> non è un tipo generico. L'unico motivo per cui è possibile specificare un tipo su cui <xref:System.Array.ForEach%2A?displayProperty=nameWithType> possa agire è che il metodo dispone di un elenco specifico di parametri di tipo. Al contrario, il metodo non generico <xref:System.Collections.Generic.List%601.ForEach%2A?displayProperty=nameWithType> appartiene alla classe generica <xref:System.Collections.Generic.List%601> e pertanto usa semplicemente il parametro di tipo della rispettiva classe. La classe è fortemente tipizzata, quindi il metodo può essere un metodo di istanza.  
  
 Il delegato generico <xref:System.Predicate%601> rappresenta un metodo che determina se un determinato elemento soddisfa i criteri specificati. È possibile usarlo con i metodi generici statici di <xref:System.Array> seguenti per cercare un elemento o un set di elementi: <xref:System.Array.Exists%2A>, <xref:System.Array.Find%2A>, <xref:System.Array.FindAll%2A>, <xref:System.Array.FindIndex%2A>, <xref:System.Array.FindLast%2A>, <xref:System.Array.FindLastIndex%2A> e <xref:System.Array.TrueForAll%2A>.  
  
 <xref:System.Predicate%601> usa inoltre i metodi di istanza non generici corrispondenti della classe generica <xref:System.Collections.Generic.List%601>.  
  
 Il delegato generico <xref:System.Comparison%601> consente di fornire una sequenza di ordinamento per gli elementi di matrice o elenco che non hanno un ordinamento nativo, oppure di eseguire l'override dell'ordinamento nativo. Creare un metodo che esegua il confronto, creare un'istanza del delegato <xref:System.Comparison%601> per rappresentare il metodo e quindi passare la matrice e il delegato al metodo generico statico <xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29?displayProperty=nameWithType>. La classe generica <xref:System.Collections.Generic.List%601> fornisce un overload del metodo di istanza corrispondente, <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29?displayProperty=nameWithType>.  
  
 Il delegato generico <xref:System.Converter%602> consente di definire una conversione tra due tipi e di convertire una matrice o un elenco di un tipo rispettivamente in una matrice o in un elenco dell'altro. Creare un metodo che converta gli elementi dell'elenco esistente in un nuovo tipo, creare un'istanza del delegato per rappresentare il metodo e usare il metodo statico generico <xref:System.Array.ConvertAll%2A?displayProperty=nameWithType> per generare una matrice del nuovo tipo a partire dalla matrice originale, oppure il metodo di istanza generico <xref:System.Collections.Generic.List%601.ConvertAll%60%601%28System.Converter%7B%600%2C%60%600%7D%29?displayProperty=nameWithType> per generare un elenco del nuovo tipo a partire dall'elenco originale.  
  
### <a name="chaining-delegates"></a>Concatenamento di delegati  
 Molti dei metodi che usano i delegati restituiscono una matrice o un elenco che è possibile passare a un altro metodo. Se ad esempio si desidera selezionare alcuni elementi di una matrice, convertirli in un nuovo tipo e salvarli in una nuova matrice, è possibile passare la matrice restituita dal metodo generico <xref:System.Array.FindAll%2A> al metodo generico <xref:System.Array.ConvertAll%2A>. Se il nuovo tipo di elemento è privo di un ordinamento naturale, è possibile passare la matrice restituita dal metodo generico <xref:System.Array.ConvertAll%2A> al metodo generico <xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [Generics](../../../docs/standard/generics/index.md)
- [Raccolte generiche in .NET Framework](../../../docs/standard/generics/collections.md)
- [Interfacce generiche](../../../docs/standard/generics/interfaces.md)
- [Covarianza e controvarianza](../../../docs/standard/generics/covariance-and-contravariance.md)
