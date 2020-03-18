---
title: Ordinamento dei dati (C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 29a5e3e685bdc73536961b7783f4986796b46bdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167907"
---
# <a name="sorting-data-c"></a>Ordinamento dei dati (C#)
Un'operazione di ordinamento consente di ordinare gli elementi di una sequenza in base a uno o più attributi. Il primo criterio di ordinamento consente di applicare un ordinamento principale agli elementi. Specificando un secondo criterio di ordinamento, è possibile ordinare gli elementi all'interno di ogni gruppo di ordinamento principale.  
  
 La figura seguente illustra i risultati di un'operazione di ordinamento alfabetico in una sequenza di caratteri:
  
 ![Immagine che illustra un'operazione di ordinamento alfabetico.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 La sezione seguente elenca i metodi dell'operatore query standard che ordina i dati.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Sintassi di espressione della query C#|Altre informazioni|  
|-----------------|-----------------|---------------------------------|----------------------|  
|OrderBy|Ordina i valori in ordine crescente.|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|OrderByDescending|Ordina i valori in ordine decrescente.|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|ThenBy|Esegue un ordinamento secondario crescente.|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|ThenByDescending|Esegue un ordinamento secondario decrescente.|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|Reverse|Inverte l'ordine degli elementi in una Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di query  
  
### <a name="primary-sort-examples"></a>Esempi di ordinamento primario  
  
#### <a name="primary-ascending-sort"></a>Ordinamento primario crescente  
 Nell'esempio seguente viene illustrato come usare la clausola `orderby` in una query LINQ per ordinare le stringhe in una matrice in base alla lunghezza di stringa, in ordine crescente.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a>Ordinamento primario decrescente  
 Nell'esempio seguente viene illustrato come usare la clausola `orderby descending` in una query LINQ per ordinare le stringhe in base alla prima lettera, in ordine decrescente.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a>Esempi di ordinamento secondario  
  
#### <a name="secondary-ascending-sort"></a>Ordinamento secondario crescente  
 Nell'esempio seguente viene illustrato come usare la clausola `orderby` in una query LINQ per eseguire un ordinamento primario e secondario delle stringhe in una matrice. Le stringhe vengono ordinate prima in base alla lunghezza e poi in base alla prima lettera della stringa, in ordine crescente.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a>Ordinamento secondario in ordine decrescente  
 L'esempio seguente illustra come usare la clausola `orderby descending` in una query LINQ per eseguire un ordinamento primario, in ordine crescente, e un ordinamento secondario, in ordine decrescente. Le stringhe vengono ordinate principalmente in base alla lunghezza e poi in base alla prima lettera della stringa.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)
- [Clausola orderby](../../../language-reference/keywords/orderby-clause.md)
- [Ordinare i risultati di una clausola join](../../../linq/order-the-results-of-a-join-clause.md)
- [Come ordinare o filtrare i dati di testo in base a parole o campi (LINQ) (C](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
