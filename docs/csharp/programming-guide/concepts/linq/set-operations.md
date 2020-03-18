---
title: Operazioni sui set (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 44a145a625b5e2e16d2469b20f8cfda1858560a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167933"
---
# <a name="set-operations-c"></a>Operazioni sui set (C#)
Le operazioni sui set in LINQ si riferiscono alle operazioni di query che generano un set di risultati basato sulla presenza o sull'assenza di elementi equivalenti all'interno delle stesse Collection oppure di Collection (o set) distinte.  
  
 La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni sui set.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Descrizione|Sintassi di espressione della query C#|Altre informazioni|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Distinct|Rimuove i valori duplicati da una Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|Except|Restituisce la differenza dei set, ovvero gli elementi di una Collection che non sono presenti in una seconda Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|Intersect|Restituisce l'intersezione di set, ovvero gli elementi presenti in ognuna delle due Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|Union|Restituisce l'unione di set, ovvero gli elementi univoci presenti in una delle due Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a>Confronto tra le operazioni sui set  
  
### <a name="distinct"></a>Distinct  
 Nell'esempio seguente viene illustrato <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> il comportamento del metodo in una sequenza di caratteri. La sequenza restituita contiene gli elementi univoci dalla sequenza di input.  
  
 ![Elemento grafico che illustra il comportamento di Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  

 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a>Except  
 Nell'esempio riportato di <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>seguito viene illustrato il comportamento di . La sequenza restituita contiene solo gli elementi dalla prima sequenza di input che non sono presenti nella seconda sequenza di input.  
  
 ![Immagine che mostra l'azione di tranne&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Mostra il comportamento di Except.")  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a>Intersect  
 Nell'esempio riportato di <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>seguito viene illustrato il comportamento di . La sequenza restituita contiene gli elementi comuni a entrambe le sequenze di input.  
  
 ![Elemento grafico che illustra l'intersezione di due sequenze.](./media/set-operations/intersection-two-sequences.png)  

[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a>Union  
 Nell'esempio seguente viene illustrata un'operazione di unione su due sequenze di caratteri. La sequenza restituita contiene gli elementi univoci da entrambe le sequenze di input.  
  
 ![Elemento grafico che illustra l'unione di due sequenze.](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Panoramica degli operatori di query standard)
- [Come combinare e confrontare raccolte di stringhe (LINQ) (C](./how-to-combine-and-compare-string-collections-linq.md)
- [Come trovare la differenza di set tra due elenchi (LINQ) (C](./how-to-find-the-set-difference-between-two-lists-linq.md)
