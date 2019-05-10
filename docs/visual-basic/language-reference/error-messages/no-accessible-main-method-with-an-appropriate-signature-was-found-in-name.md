---
title: Impossibile trovare in '<name>' un metodo 'Main' accessibile con una firma appropriata
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 559c905d1e2e2de4500771a93d6116f9630011ba
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591987"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>È stato trovato alcun metodo 'Main' accessibile con una firma appropriata '\<nome >'
Le applicazioni della riga di comando devono avere un `Sub Main` definito. `Main` deve essere dichiarato come `Public Shared` se è definito in una classe o come `Public` se definita in un modulo.  
  
 **ID errore:** BC30737  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Definire un `Public Sub Main` procedure per il progetto. Dichiara la classe come `Shared` se e solo se viene definita in una classe.  
  
## <a name="see-also"></a>Vedere anche

- [Struttura di un programma Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
