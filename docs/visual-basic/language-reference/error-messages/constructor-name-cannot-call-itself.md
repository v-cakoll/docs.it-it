---
title: Il costruttore '<name>' non può chiamare se stesso
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 6abb6dde624e129b52fefecf8c51e6cde2567ae1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409803"
---
# <a name="constructor-name-cannot-call-itself"></a>Il costruttore '\<name>' non può chiamare se stesso
Una `Sub New` routine in una classe o in una struttura chiama se stessa.  
  
 Lo scopo di un costruttore è di inizializzare un'istanza di una classe o una struttura quando viene creata per la prima volta. Una classe o una struttura può avere più costruttori, purché tutti abbiano elenchi di parametri diversi. Un costruttore è autorizzato a chiamare un altro costruttore per eseguirne la funzionalità oltre a se stesso. Tuttavia, non è significativo per un costruttore chiamare se stesso e in realtà comporterebbe una ricorsione infinita se consentito.  
  
 **ID errore:** BC30298  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Controllare l'elenco di parametri del costruttore chiamato. Deve essere diverso da quello del costruttore che effettua la chiamata.  
  
2. Se non si intende chiamare un costruttore diverso, rimuovere `Sub New` completamente la chiamata.  
  
## <a name="see-also"></a>Vedere anche

- [Durata degli oggetti: come creare e distruggere oggetti](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
