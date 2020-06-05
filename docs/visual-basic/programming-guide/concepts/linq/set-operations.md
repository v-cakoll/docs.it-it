---
title: Operazioni sui set
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: b6ff14794343ae7623ee38894cef02cfc0a2a597
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406820"
---
# <a name="set-operations-visual-basic"></a>Operazioni set (Visual Basic)

Le operazioni sui set in LINQ si riferiscono alle operazioni di query che generano un set di risultati basato sulla presenza o sull'assenza di elementi equivalenti all'interno delle stesse Collection oppure di Collection (o set) distinte.

La sezione seguente elenca i metodi dell'operatore query standard che eseguono operazioni sui set.

## <a name="methods"></a>Metodi

|Nome metodo|Descrizione|Visual Basic sintassi delle espressioni di query|Altre informazioni|
|-----------------|-----------------|------------------------------------------|----------------------|
|Distinct|Rimuove i valori duplicati da una Collection.|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|Except|Restituisce la differenza dei set, ovvero gli elementi di una Collection che non sono presenti in una seconda Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|Intersect|Restituisce l'intersezione di set, ovvero gli elementi presenti in ognuna delle due Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|Union|Restituisce l'unione di set, ovvero gli elementi univoci presenti in una delle due Collection.|Non applicabile.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a>Confronto tra le operazioni sui set

### <a name="distinct"></a>Distinct

Nella figura seguente viene illustrato il comportamento del metodo <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> su una sequenza di caratteri. La sequenza restituita contiene gli elementi univoci dalla sequenza di input.

![Elemento grafico che illustra il comportamento di Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a>Except

Nella figura seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>. La sequenza restituita contiene solo gli elementi dalla prima sequenza di input che non sono presenti nella seconda sequenza di input.

![Immagine che mostra l'azione di except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Mostra il comportamento di eccetto.")

### <a name="intersect"></a>Intersect

Nella figura seguente viene illustrato il comportamento di <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>. La sequenza restituita contiene gli elementi comuni a entrambe le sequenze di input.

![Elemento grafico che illustra l'intersezione di due sequenze.](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a>Union

La figura seguente illustra un'operazione di unione tra due sequenze di caratteri. La sequenza restituita contiene gli elementi univoci da entrambe le sequenze di input.

![Elemento grafico che illustra l'unione di due sequenze.](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a>Esempio di sintassi delle espressioni di query

Nell'esempio seguente viene usata la `Distinct` clausola in una query LINQ per restituire i numeri univoci da un elenco di numeri interi.

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)
- [Clausola Distinct](../../../language-reference/queries/distinct-clause.md)
- [Procedura: combinare e confrontare raccolte di stringhe (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md)
- [Procedura: trovare la differenza dei set tra due elenchi (LINQ) (Visual Basic)](how-to-find-the-set-difference-between-two-lists-linq.md)
