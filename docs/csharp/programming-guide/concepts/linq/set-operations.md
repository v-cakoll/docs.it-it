---
title: Operazioni sui set (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 9e507bbaa39bf040a8ce1564630fb5fbb8c0dbe4
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408912"
---
# <a name="set-operations-c"></a>Operazioni sui set (C#)
Le operazioni sui set in LINQ si riferiscono alle operazioni di query che generano un set di risultati basato sulla presenza o sull'assenza di elementi equivalenti all'interno delle stesse Collection oppure di Collection (o set) distinte.  
  
 La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni sui set.  
  
## <a name="methods"></a>Metodi  
  
|Nome metodo|Description|Sintassi di espressione della query C#|Altre informazioni|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Distinct|Rimuove i valori duplicati da una Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|Eccezione|Restituisce la differenza dei set, ovvero gli elementi di una Collection che non sono presenti in una seconda Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|Interseca|Restituisce l'intersezione di set, ovvero gli elementi presenti in ognuna delle due Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|Unione|Restituisce l'unione di set, ovvero gli elementi univoci presenti in una delle due Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a>Confronto tra le operazioni sui set  
  
### <a name="distinct"></a>Distinct  
 Nella figura seguente viene illustrato il comportamento del metodo <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> su una sequenza di caratteri. La sequenza restituita contiene gli elementi univoci dalla sequenza di input.  
  
 ![Elemento grafico che illustra il comportamento di Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)  
  
### <a name="except"></a>Eccezione  
 Nella figura seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>. La sequenza restituita contiene solo gli elementi dalla prima sequenza di input che non sono presenti nella seconda sequenza di input.  
  
 ![Grafico che mostra l'azione di Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Mostra il comportamento di Except.")  
  
### <a name="intersect"></a>Interseca  
 Nella figura seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>. La sequenza restituita contiene gli elementi comuni a entrambe le sequenze di input.  
  
 ![Elemento grafico che illustra l'intersezione di due sequenze.](./media/set-operations/intersection-two-sequences.png)  
 
### <a name="union"></a>Unione  
 La figura seguente illustra un'operazione di unione tra due sequenze di caratteri. La sequenza restituita contiene gli elementi univoci da entrambe le sequenze di input.  
  
 ![Elemento grafico che illustra l'unione di due sequenze.](./media/set-operations/union-operation-two-sequences.png)  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori di query standard (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Procedura: Combinare e confrontare raccolte di stringhe (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [Procedura: Trovare la differenza dei set tra due elenchi (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
