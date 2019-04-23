---
title: Numero o nome file errato
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 2e5d4a3ddd66df85dc4758e22b36ac1ed495659a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322160"
---
# <a name="bad-file-name-or-number"></a>Numero o nome file errato
Si è verificato un errore durante il tentativo di accedere al file specificato. Tra le possibili cause di questo errore sono:  
  
-   Un'istruzione fa riferimento a un file con un nome file o un numero che non è stato specificato nel `FileOpen` istruzione o che è stato specificato un `FileOpen` istruzione ma è stata successivamente chiusi.  
  
-   Un'istruzione fa riferimento a un file con un numero compreso nell'intervallo dei numeri di file.  
  
-   Un'istruzione fa riferimento a un nome file o un numero non valido.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Assicurarsi che il nome del file è specificato un `FileOpen` istruzione. Si noti che se è stata richiamata la `FileClose` istruzione senza argomenti, si potrebbero avere inavvertitamente chiusi tutti i file aperti.  
  
2. Il codice durante la generazione di numeri di file modo algoritmico, verificare che i numeri siano validi.  
  
3. Controllare i nomi di file per assicurarsi che siano conformi alle convenzioni del sistema operativo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
