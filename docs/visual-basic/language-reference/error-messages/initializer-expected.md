---
title: Previsto inizializzatore
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 9d786fd1e929129c420b7bec62efd0bd445d85eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586386"
---
# <a name="initializer-expected"></a>Previsto inizializzatore
Si è provato a dichiarare un'istanza di una classe utilizzando un inizializzatore di oggetto in cui l'inizializzazione di elenco è vuoto, come illustrato nell'esempio seguente.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 Almeno un campo o una proprietà deve essere inizializzato nell'elenco di inizializzatori, come illustrato nell'esempio seguente.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **ID errore:** BC30996  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Inizializzare almeno un campo o proprietà nell'inizializzatore o non utilizzare un inizializzatore di oggetto.  
  
## <a name="see-also"></a>Vedere anche  
 [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
