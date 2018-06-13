---
title: Ordinale non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 12d73b33e3c025b40c98d84e3507af7be1e1e91a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593603"
---
# <a name="ordinal-is-not-valid"></a>Ordinale non valido
La chiamata a una libreria di collegamento dinamico (DLL) indica di usare un numero anziché un nome di stored procedure, tramite il `#num` sintassi. Questo errore sono le seguenti cause possibili:  
  
-   Un tentativo di convertire il `#num` espressione in un ordinale non è riuscito.  
  
-   Il `#num` specificato non specifica alcuna funzione nella DLL.  
  
-   Una libreria dei tipi è una dichiarazione non valida risultante utilizzo interno di un numero ordinale non valido.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che l'espressione rappresenta un numero valido o chiamare la routine in base al nome.  
  
2.  Assicurarsi che `#num` identifica una funzione nella DLL valida.  
  
3.  Isolare la chiamata di routine che provoca il problema Commentando il codice. Scrivere un `Declare` istruzione per la procedura e il problema al fornitore della libreria dei tipi di report.  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)
