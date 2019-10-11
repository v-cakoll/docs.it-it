---
title: <proceduresignature1> non è conforme a CLS perché esegue l'overload di <proceduresignature2> che differisce da esso solo per la matrice dei tipi di parametro matrice o per il numero di dimensioni dei tipi di parametro matrice
ms.date: 07/20/2015
f1_keywords:
- vbc40035
- bc40035
helpviewer_keywords:
- BC40035
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
ms.openlocfilehash: 6143ebfbe7f131b0e196e531ed4282c8333be4ea
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250175"
---
# <a name="proceduresignature1-is-not-cls-compliant-because-it-overloads-proceduresignature2-which-differs-from-it-only-by-array-of-array-parameter-types-or-by-the-rank-of-the-array-parameter-types"></a>il > \<proceduresignature1 non è conforme a CLS perché viene sottoposto a overload \<proceduresignature2 > che differisce da esso solo per matrice di tipi di parametro di matrice o per il rango dei tipi di parametro di matrice

Una routine o una proprietà è contrassegnata come `<CLSCompliant(True)>` quando esegue l'override di un'altra routine o proprietà e l'unica differenza tra gli elenchi di parametri è il livello di nidificazione di una matrice di matrici o il rango di una matrice.
  
 Nelle dichiarazioni seguenti la seconda e la terza dichiarazione generano questo errore:
  
 `Overloads Sub ProcessArray(arrayParam() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam()() As Integer)`  
  
 `Overloads Sub ProcessArray(arrayParam(,) As Integer)`  
  
 La seconda dichiarazione modifica il parametro unidimensionale originale `arrayParam` in una matrice di matrici. La terza dichiarazione cambia `arrayParam` in una matrice bidimensionale (Rank 2). Sebbene Visual Basic consentano gli overload di differire solo per una di queste modifiche, tale overload non è conforme all' [indipendenza del linguaggio e ai componenti indipendenti dal linguaggio](../../../standard/language-independence-and-language-independent-components.md) (CLS).  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute> , l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40035  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se è necessaria la conformità a CLS, definire gli overload per distinguerli tra loro in più modi rispetto alle modifiche citate in questa pagina della guida.
- Se è necessario che gli overload differiscano solo per le modifiche citate in questa pagina della guida, rimuovere il <xref:System.CLSCompliantAttribute> dalle definizioni o contrassegnarle come `<CLSCompliant(False)>`.
  
## <a name="see-also"></a>Vedere anche

- [Overload della routine](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [Overload](../modifiers/overloads.md)
