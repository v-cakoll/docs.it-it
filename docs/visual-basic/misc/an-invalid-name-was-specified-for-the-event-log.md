---
title: È stato specificato un nome non valido per il log eventi
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 05f37239510482de218847f069dc74cbef91f398
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609173"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>È stato specificato un nome non valido per il log eventi
È stato specificato un nome non valido per il log eventi. Generalmente è l'effetto della presenza di caratteri non validi nel nome, di un nome file vuoto o di un nome file troppo lungo.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se la lunghezza del nome specificato supera otto caratteri, accertarsi che non vi sia un conflitto con i nomi di altri log eventi. Quando si determina se il nome è univoco vengono presi in considerazione solo i primi otto caratteri.  
  
- Se si fornisce un percorso, accertarsi che venga analizzato correttamente.  
  
- Verificare che il nome non contenga caratteri non validi. I caratteri che non è possibile usare in un nome file comprendono `<`, `>`, `:`, `"`, `/`, `\`e `|`.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Analizzare percorsi di file](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [Procedura: Rinominare un file](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
