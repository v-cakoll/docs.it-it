---
title: L'uso dell'istanza predefinita di una classe nel costruttore della classe potrebbe generare una chiamata ricorsiva infinita
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: b4cae7802019cba569cf15517b1e948266a576f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631438"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>L'uso dell'istanza predefinita di una classe nel costruttore della classe potrebbe generare una chiamata ricorsiva infinita
Nel costruttore della classe è stata usata un'istanza predefinita di una classe. Questo può causare una chiamata ricorsiva infinita, detta anche ciclo infinito.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Rimuovere l'istanza predefinita dal costruttore della classe.  
  
## <a name="see-also"></a>Vedere anche
- [Costruttori](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
