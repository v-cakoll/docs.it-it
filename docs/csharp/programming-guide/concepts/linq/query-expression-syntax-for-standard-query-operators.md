---
title: Sintassi di espressione di query per operatori di query standard (C#)
ms.date: 07/20/2015
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
ms.openlocfilehash: dac63ae165b88924cb0e91336571173f764569ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591437"
---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a>Sintassi di espressione di query per operatori di query standard (C#)
Alcuni degli operatori di query standard usati più di frequente dispongono di una sintassi dedicata delle parole chiave per i linguaggi C# che consente di chiamare gli operatori come parte di un'espressione di *query*. Un'espressione di query rappresenta un modo diverso e più leggibile per esprimere una query rispetto alla sintassi equivalente *basata su metodo*. Le clausole di espressione di query vengono convertite in chiamate ai metodi di query in fase di compilazione.  
  
## <a name="query-expression-syntax-table"></a>Tabella della sintassi di espressione di query  
 La tabella seguente elenca gli operatori di query standard che hanno clausole di espressione di query equivalenti.  
  
|Metodo|Sintassi di espressione della query C#|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|Usare una variabile di intervallo tipizzata in modo esplicito, ad esempio:<br /><br /> `from int i in numbers`<br /><br /> (Per ulteriori informazioni, vedere la [clausola from](../../../language-reference/keywords/from-clause.md).|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> -oppure-<br /><br /> `group … by … into …`<br /><br /> (Per ulteriori informazioni, vedere [la clausola group](../../../language-reference/keywords/group-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> Per altre informazioni, vedere [Clausola join](../../../language-reference/keywords/join-clause.md).|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> Per altre informazioni, vedere [Clausola join](../../../language-reference/keywords/join-clause.md).|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> (Per ulteriori informazioni, vedere [clausola orderby](../../../language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> (Per ulteriori informazioni, vedere [clausola orderby](../../../language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> Per altre informazioni, vedere [Clausola select](../../../language-reference/keywords/select-clause.md).|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|Più clausole `from`.<br /><br /> (Per ulteriori informazioni, vedere la [clausola from](../../../language-reference/keywords/from-clause.md).|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> (Per ulteriori informazioni, vedere [clausola orderby](../../../language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> (Per ulteriori informazioni, vedere [clausola orderby](../../../language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> Per altre informazioni, vedere [Clausola where](../../../language-reference/keywords/where-clause.md).|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)
- [Classificazione degli operatori di query standard in base alla modalità di esecuzione](./classification-of-standard-query-operators-by-manner-of-execution.md)
