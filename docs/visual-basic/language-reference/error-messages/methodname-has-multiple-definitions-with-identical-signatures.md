---
title: Il metodo '<methodname>' contiene più definizioni con firme identiche
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 3b397711cc2fb1fd0c1dfd76899b162ab5fc1542
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397233"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a>Il metodo '\<methodname>' contiene più definizioni con firme identiche
Una `Function` `Sub` dichiarazione di routine o usa il nome della procedura e l'elenco di argomenti identici di una dichiarazione precedente. Una delle possibili cause è il tentativo di eseguire l'overload della routine originale. Le routine di overload devono contenere elenchi di argomenti diversi.  
  
 **ID errore:** BC30269  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Modificare il nome della stored procedure o l'elenco degli argomenti oppure rimuovere la dichiarazione duplicata.  
  
## <a name="see-also"></a>Vedere anche

- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Considerazioni sull'overload di routine](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
