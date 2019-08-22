---
title: L'uso dell'istanza predefinita di una classe nel costruttore della classe potrebbe generare una chiamata ricorsiva infinita
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: cec3d3d462822ca571cab59a2e4d7e730d2aec46
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664374"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a>L'uso dell'istanza predefinita di una classe nel costruttore della classe potrebbe generare una chiamata ricorsiva infinita
Nel costruttore della classe è stata usata un'istanza predefinita di una classe. Questo può causare una chiamata ricorsiva infinita, detta anche ciclo infinito.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Rimuovere l'istanza predefinita dal costruttore della classe.  
  
## <a name="see-also"></a>Vedere anche

- [Costruttori](../programming-guide/concepts/object-oriented-programming.md#constructors)
