---
title: Impossibile trovare in '<name>' un metodo 'Main' accessibile con una firma appropriata
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6760b931ceb2ad5c2c04169d664da8629badc487
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409413"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>Impossibile trovare in '\<name>' un metodo 'Main' accessibile con una firma appropriata
Per le applicazioni da riga di comando deve essere `Sub Main` definito. `Main`deve essere dichiarato come `Public Shared` se fosse definito in una classe o come se fosse `Public` definito in un modulo.  
  
 **ID errore:** BC30737  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Definire una `Public Sub Main` procedura per il progetto. Dichiararla come `Shared` se fosse e solo se viene definita all'interno di una classe.  
  
## <a name="see-also"></a>Vedere anche

- [Struttura di un programma Visual Basic](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Procedure](../../programming-guide/language-features/procedures/index.md)
