---
title: Numero o nome file errato
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
