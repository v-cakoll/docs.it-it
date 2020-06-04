---
title: Ordinale non valido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 7b9bd8435b56dd5e33d14eb35d76aacc7d60c8b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413053"
---
# <a name="ordinal-is-not-valid"></a>Ordinale non valido
La chiamata a una libreria a collegamento dinamico (DLL) indica di usare un numero anziché un nome di routine, usando la `#num` sintassi. Questo errore presenta le possibili cause seguenti:  
  
- Tentativo di conversione dell' `#num` espressione in un ordinale non riuscito.  
  
- Il `#num` parametro specificato non specifica alcuna funzione nella dll.  
  
- Una libreria dei tipi ha una dichiarazione non valida che comporta l'uso interno di un numero ordinale non valido.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che l'espressione rappresenti un numero valido o chiamare la procedura in base al nome.  
  
2. Assicurarsi che `#num` identifichi una funzione valida nella dll.  
  
3. Isolare la chiamata di procedura che causa il problema impostando come commento il codice. Scrivere un' `Declare` istruzione per la procedura e segnalare il problema al fornitore della libreria dei tipi.  
  
## <a name="see-also"></a>Vedere anche

- [Declare Statement](../statements/declare-statement.md)
