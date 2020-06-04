---
title: Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: d01c30571fc34e142300ac8706c56d5e99175fcf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397207"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a>Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi
`Module`le istruzioni devono essere visualizzate nella parte superiore del file di origine immediatamente dopo `Option` `Imports` le istruzioni and, gli attributi globali e le dichiarazioni dello spazio dei nomi, ma prima di tutte le altre dichiarazioni.  
  
 **ID errore:** BC30617  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Spostare l'istruzione `Module` all'inizio della dichiarazione dello spazio dei nomi o del file di origine.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Module](../statements/module-statement.md)
