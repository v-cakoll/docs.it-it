---
title: Ordinale non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 28f78161e14604c1f59872801855ccc918faec58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299254"
---
# <a name="ordinal-is-not-valid"></a>Ordinale non valido
La chiamata a una libreria di collegamento dinamico (DLL) indica di usare un numero anziché un nome di procedura, utilizzando il `#num` sintassi. Questo errore sono le seguenti cause possibili:  
  
-   Un tentativo di convertire il `#num` espressione da un numero ordinale non è riuscito.  
  
-   Il `#num` specificato non viene specificata alcuna funzione di DLL.  
  
-   Una libreria dei tipi dispone di una dichiarazione non valida conseguente uso interno di un numero ordinale non valido.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che l'espressione rappresenta un numero valido oppure chiamare la routine in base al nome.  
  
2. Assicurarsi che `#num` identifica una funzione nella DLL valida.  
  
3. Isolare la chiamata di procedura provoca il problema Commentando il codice. Scrivere un `Declare` istruzione per la routine e di segnalare il problema al fornitore della libreria dei tipi.  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
