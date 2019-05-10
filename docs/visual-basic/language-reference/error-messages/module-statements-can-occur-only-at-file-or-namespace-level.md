---
title: Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: fc3c102dbfe7c55e66093421bc11379d48ba000d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592090"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a>Le istruzioni 'Module' possono trovarsi solo a livello di file o di spazio dei nomi
`Module` devono essere visualizzate nella parte superiore del file di origine immediatamente dopo aver `Option` e `Imports` istruzioni, gli attributi globali e le dichiarazioni dello spazio dei nomi, ma prima di tutte le altre dichiarazioni.  
  
 **ID errore:** BC30617  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Spostare l'istruzione `Module` all'inizio della dichiarazione dello spazio dei nomi o del file di origine.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)
