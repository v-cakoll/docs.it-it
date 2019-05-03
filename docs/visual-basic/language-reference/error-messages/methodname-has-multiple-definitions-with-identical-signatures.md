---
title: Il metodo '<methodname>' contiene più definizioni con firme identiche
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: fe8d1d8e11e25bcd79894ed82a57dd06748c3d68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920900"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a>'\<NomeMetodo >' contiene più definizioni con firme identiche
Oggetto `Function` o `Sub` dichiarazione di routine Usa la procedura identico nome ed elenco di argomenti come una dichiarazione precedente. Una possibile causa è un tentativo di eseguire l'overload di routine originale. Le routine di overload devono avere gli elenchi di argomenti diversi.  
  
 **ID errore:** BC30269  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Modificare il nome della routine o l'elenco di argomenti oppure rimuovere la dichiarazione duplicata.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti a elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Considerazioni sull'overload di routine](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
