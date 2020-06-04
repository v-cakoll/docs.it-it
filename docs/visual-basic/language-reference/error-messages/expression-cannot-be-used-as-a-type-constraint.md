---
title: Impossibile utilizzare '<expression>' come vincolo di tipo
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: e2ba411a5f0db21539a9cf99c7645b8c9309caab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409556"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a>Impossibile utilizzare '\<expression>' come vincolo di tipo
Un elenco di vincoli comprende un'espressione che non rappresenta un vincolo valido per un parametro di tipo.  
  
 Un elenco di vincoli impone requisiti per l'argomento di tipo passato al parametro di tipo. Si possono specificare i requisiti seguenti in qualsiasi combinazione:  
  
- L'argomento di tipo deve implementare una o più interfacce  
  
- L'argomento di tipo deve ereditare al massimo da una classe  
  
- L'argomento di tipo deve esporre un costruttore senza parametri a cui il codice di creazione possa accedere (includere il vincolo `New` )  
  
 Se non si include alcuna classe o interfaccia specifica nell'elenco di vincoli, è possibile imporre un requisito più generale specificando una delle condizioni seguenti:  
  
- L'argomento di tipo deve essere un tipo valore (includere il vincolo `Structure` )  
  
- L'argomento di tipo deve essere un tipo riferimento (includere il vincolo `Class` )  
  
 Non è possibile specificare sia `Structure` che `Class` per lo stesso parametro di tipo e non è possibile specificare uno dei due vincoli più volte.  
  
 **ID errore:** BC32061  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Verificare che l'espressione e i suoi elementi siano digitati correttamente.  
  
- Se l'espressione non soddisfa l'elenco di requisiti precedente, rimuoverla dall'elenco di vincoli.  
  
- Se l'espressione fa riferimento a un'interfaccia o a una classe, verificare che il compilatore possa accedere a quell'interfaccia o a quella classe. Potrebbe essere necessario qualificarne il nome e anche aggiungere un riferimento al progetto. Per ulteriori informazioni, vedere "riferimenti ai progetti" in [riferimenti a elementi dichiarati](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Vedere anche

- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
