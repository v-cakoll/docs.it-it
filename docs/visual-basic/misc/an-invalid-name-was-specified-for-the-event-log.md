---
title: È stato specificato un nome non valido per il log eventi
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 8b6df077f15744cd2c34fb9e7e148b02ea27d5bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598063"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>È stato specificato un nome non valido per il log eventi
È stato specificato un nome non valido per il log eventi. Generalmente è l'effetto della presenza di caratteri non validi nel nome, di un nome file vuoto o di un nome file troppo lungo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se la lunghezza del nome specificato supera otto caratteri, accertarsi che non vi sia un conflitto con i nomi di altri log eventi. Quando si determina se il nome è univoco vengono presi in considerazione solo i primi otto caratteri.  
  
-   Se si fornisce un percorso, accertarsi che venga analizzato correttamente.  
  
-   Verificare che il nome non contenga caratteri non validi. I caratteri che non è possibile usare in un nome file comprendono `<`, `>`, `:`, `"`, `/`, `\`e `|`.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: analizzare percorsi di file](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [Procedura: rinominare un file](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 
