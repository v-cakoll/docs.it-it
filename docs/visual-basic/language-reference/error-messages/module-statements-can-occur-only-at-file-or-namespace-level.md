---
title: Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bf0239422fb5a98e4670aea407f684753d3a7ea4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825443"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a>Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi
`Module` devono essere visualizzate nella parte superiore del file di origine immediatamente dopo aver `Option` e `Imports` istruzioni, gli attributi globali e le dichiarazioni dello spazio dei nomi, ma prima di tutte le altre dichiarazioni.  
  
 **ID errore:** BC30617  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Spostare l'istruzione `Module` all'inizio della dichiarazione dello spazio dei nomi o del file di origine.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)
