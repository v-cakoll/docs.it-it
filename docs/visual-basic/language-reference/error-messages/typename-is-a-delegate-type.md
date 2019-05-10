---
title: "'<typename>' è un tipo delegato"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 45dc0403468fa40888a6c5e6bdfe6ca782e98325
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664173"
---
# <a name="typename-is-a-delegate-type"></a>'\<nomeTipo >' è un tipo delegato
'\<nomeTipo >' è un tipo delegato. Creazione di delegati consente solo una singola espressione AddressOf come un elenco di argomenti. Spesso un'espressione AddressOf può essere utilizzata invece una costruzione di delegato.  
  
 Oggetto `New` clausola che crea un'istanza di una classe delegata fornisce un elenco di argomenti non valido al costruttore di delegato.  
  
 È possibile fornire una sola `AddressOf` espressione quando si crea una nuova istanza di delegato.  
  
 Questo errore può verificarsi se non si passano argomenti al costruttore di delegato, se si passa più di un argomento, o se si passa un singolo argomento che non è valida `AddressOf` espressione.  
  
 **ID errore:** BC32008  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare una sola `AddressOf` espressione nell'elenco di argomenti per la classe delegata nel `New` clausola.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore New](../../../visual-basic/language-reference/operators/new-operator.md)
- [Operatore AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegati](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Procedura: Richiamare un metodo delegato](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
