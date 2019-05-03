---
title: Impossibile trovare in '<name>' un metodo 'Main' accessibile con una firma appropriata
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: f5053bddf4b9ba791ad6d0733e1dd89c4ded91bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918268"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>È stato trovato alcun metodo 'Main' accessibile con una firma appropriata '\<nome >'
Le applicazioni della riga di comando devono avere un `Sub Main` definito. `Main` deve essere dichiarato come `Public Shared` se è definito in una classe o come `Public` se definita in un modulo.  
  
 **ID errore:** BC30737  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Definire un `Public Sub Main` procedure per il progetto. Dichiara la classe come `Shared` se e solo se viene definita in una classe.  
  
## <a name="see-also"></a>Vedere anche

- [Struttura di un programma Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
