---
title: La classe non supporta l'automazione o l'interfaccia prevista
ms.date: 07/20/2015
f1_keywords:
- vbrID430
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
ms.openlocfilehash: 28089647e8a67d2da55ddd12288b298bcace66c0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816187"
---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>La classe non supporta l'automazione o l'interfaccia prevista
La classe specificata nella funzione `GetObject` o `CreateObject` non ha esposto un'interfaccia di programmabilità oppure è stato modificato un progetto da .dll a .exe o viceversa.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Consultare la documentazione dell'applicazione che ha creato l'oggetto per verificare l'eventuale presenza di limitazioni sull'uso dell'automazione.  
  
2.  Se è stato modificato un progetto da .dll a .exe o viceversa, è necessario annullare manualmente la registrazione del precedente .dll o .exe.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Talk to Us](/visualstudio/ide/talk-to-us) (Comunicazioni con Microsoft)
