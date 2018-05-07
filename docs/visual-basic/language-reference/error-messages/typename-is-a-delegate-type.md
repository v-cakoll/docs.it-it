---
title: '&#39;&lt;TypeName&gt; &#39; è un tipo delegato'
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: c6d4244ce72dedee50b65ba19978149ce86b9e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39;&lt;TypeName&gt; &#39; è un tipo delegato
'\<nomeTipo >' è un tipo delegato. Creazione di delegati consente solo una singola espressione AddressOf come un elenco di argomenti. Spesso è possibile utilizzare un'espressione AddressOf anziché una costruzione di delegati.  
  
 Oggetto `New` clausola che crea un'istanza di una classe delegata fornisce un elenco di argomenti non valido al costruttore di delegato.  
  
 È possibile fornire una sola `AddressOf` espressione durante la creazione di una nuova istanza di delegato.  
  
 Questo errore può verificarsi se non si passano argomenti al costruttore di delegato, se si passano più argomenti, o se si passa un singolo argomento che non è un valido `AddressOf` espressione.  
  
 **ID errore:** BC32008  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Usare un singolo `AddressOf` espressione nell'elenco di argomenti per la classe delegata nel `New` clausola.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore New](../../../visual-basic/language-reference/operators/new-operator.md)  
 [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Procedura: Richiamare un metodo delegato](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
