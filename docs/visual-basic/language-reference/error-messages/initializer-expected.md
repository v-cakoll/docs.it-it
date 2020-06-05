---
title: Previsto inizializzatore
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 13fa8917f228661fc44f5e0920d91c596e250c38
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402837"
---
# <a name="initializer-expected"></a>Previsto inizializzatore
Si è provato a dichiarare un'istanza di una classe usando un inizializzatore di oggetto in cui l'elenco di inizializzazione è vuoto, come illustrato nell'esempio seguente.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 È necessario inizializzare almeno un campo o una proprietà nell'elenco di inizializzatori, come illustrato nell'esempio seguente.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **ID errore:** BC30996  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Inizializzare almeno un campo o una proprietà nell'inizializzatore oppure non usare un inizializzatore di oggetto.  
  
## <a name="see-also"></a>Vedere anche

- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
