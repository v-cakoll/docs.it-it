---
title: L'uso dell'istanza predefinita di una classe nel costruttore della classe potrebbe generare una chiamata ricorsiva infinita
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 14c498bf3067415f8de2afaeaaa57cf3f28ae857
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022454"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>L'uso dell'istanza predefinita di una classe nel costruttore della classe potrebbe generare una chiamata ricorsiva infinita
Nel costruttore della classe è stata usata un'istanza predefinita di una classe. Questo può causare una chiamata ricorsiva infinita, detta anche ciclo infinito.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere l'istanza predefinita dal costruttore della classe.  
  
## <a name="see-also"></a>Vedere anche

- [Costruttori](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
