---
title: "&lt;proceduresignature1&gt; non è conforme a CLS perché esegue l'overload &lt;proceduresignature2&gt; che differisce da esso solo per la matrice di tipi di parametro matrice o per numero di dimensioni dei tipi di parametro matrice"
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 0f4eaa09c3d04af350637fba0d672f55040a6466
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626849"
---
# <a name="ltproceduresignature1gt-is-not-cls-compliant-because-it-overloads-ltproceduresignature2gt-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>&lt;proceduresignature1&gt; non è conforme a CLS perché esegue l'overload &lt;proceduresignature2&gt; che differisce da esso solo per la matrice di tipi di parametro matrice o per numero di dimensioni dei tipi di parametro matrice
Una routine o proprietà è contrassegnata come `<CLSCompliant(True)>` quando esegue l'override di un'altra proprietà o routine e l'unica differenza tra gli elenchi dei parametri è il livello di nidificazione di una matrice di matrici o il numero di dimensioni di una matrice.  
  
 Nelle seguenti dichiarazioni, le dichiarazioni di seconda e terza generano questo errore.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 La seconda dichiarazione modifica parametro originale dell'unidimensionale `arrayParam` a una matrice di matrici. La terza dichiarazione modifica `arrayParam` a una matrice bidimensionale (rank 2). Anche se Visual Basic consente l'overload a differiscono solo per una di queste modifiche, questo tipo di overload non è conforme con la [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40035  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se necessaria la conformità a CLS, definire l'overload per differenziarsi in più modi rispetto a quelle elencate in questa pagina della Guida.  
  
-   Se è necessario che gli overload sono diversi solo per le modifiche citate in questo argomento della Guida di pagina, rimuovere il <xref:System.CLSCompliantAttribute> dalle relative definizioni o contrassegnarli come `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>Vedere anche

- [Overload della routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Overload](../../../visual-basic/language-reference/modifiers/overloads.md)
