---
title: Numero o nome file errato
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 903be68e71ad590b4b669545afd077175534ef4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585567"
---
# <a name="bad-file-name-or-number"></a>Numero o nome file errato
Si è verificato un errore durante il tentativo di accedere al file specificato. Le cause possibili di questo errore sono:  
  
-   Un'istruzione fa riferimento a un file con un nome file o un numero non è stato specificato nel `FileOpen` istruzione o che è stato specificato un `FileOpen` istruzione ma successivamente è chiuso.  
  
-   Un'istruzione fa riferimento a un file con un numero che è compreso nell'intervallo dei numeri di file.  
  
-   Un'istruzione fa riferimento a un nome file o un numero che non è valido.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che il nome del file è specificato un `FileOpen` istruzione. Si noti che se è stato richiamato il `FileClose` istruzione senza argomenti, sono stati inavvertitamente chiusi tutti i file aperti.  
  
2.  Il codice durante la generazione di numeri di file modo algoritmico, verificare che i numeri siano validi.  
  
3.  Controllare i nomi di file per assicurarsi che siano conformi alle convenzioni del sistema operativo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
