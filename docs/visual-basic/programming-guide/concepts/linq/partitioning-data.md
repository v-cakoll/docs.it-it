---
title: Partizionamento dei dati
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 34749f9d7b137bade66b6103650871246c3cc532
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406846"
---
# <a name="partitioning-data-visual-basic"></a>Partizionamento dei dati (Visual Basic)
Il partizionamento in LINQ è l'operazione di divisione di una sequenza di input in due sezioni senza ridisposizione degli elementi e la successiva restituzione di una delle sezioni.  
  
 La figura seguente illustra i risultati di tre diverse operazioni di partizionamento in una sequenza di caratteri. La prima operazione restituisce i primi tre elementi nella sequenza. La seconda operazione ignora i primi tre elementi e restituisce gli elementi rimanenti. La terza operazione ignora i primi due elementi nella sequenza e restituisce i tre elementi successivi.  
  
 ![Figura che illustra tre operazioni di partizionamento LINQ.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 Nella sezione seguente sono elencati i metodi degli operatori di query standard che eseguono la partizione delle sequenze.  
  
## <a name="operators"></a>Operatori  
  
|Nome operatore|Descrizione|Visual Basic sintassi delle espressioni di query|Altre informazioni|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Ignora|Ignora gli elementi fino a una posizione specificata in una sequenza.|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Ignora gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Accetta gli elementi fino a una posizione specificata in una sequenza.|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Accetta gli elementi in base a una funzione di predicato fino a quando un elemento non soddisfa la condizione.|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Esempi di sintassi delle espressioni di query  
  
### <a name="skip"></a>Ignora  
 Nell'esempio di codice seguente viene usata la `Skip` clausola in Visual Basic per ignorare le prime quattro stringhe in una matrice di stringhe prima di restituire le altre stringhe nella matrice.  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a>SkipWhile  
 Nell'esempio di codice seguente viene usata la `Skip While` clausola in Visual Basic per ignorare le stringhe in una matrice mentre la prima lettera della stringa è "a". Vengono restituite le stringhe rimanenti nella matrice.  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a>Take  
 Nell'esempio di codice seguente viene usata la `Take` clausola in Visual Basic per restituire le prime due stringhe in una matrice di stringhe.  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a>TakeWhile  
 Nell'esempio di codice seguente viene usata la `Take While` clausola in Visual Basic per restituire stringhe da una matrice mentre la lunghezza della stringa è cinque o meno.  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)
- [Clausola Skip](../../../language-reference/queries/skip-clause.md)
- [Clausola Skip While](../../../language-reference/queries/skip-while-clause.md)
- [Clausola Take](../../../language-reference/queries/take-clause.md)
- [Clausola Take While](../../../language-reference/queries/take-while-clause.md)
