---
title: Numero o nome file errato
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 11e866d9a8da7ad1ecc5f788fc31f6ac96d32f2c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409829"
---
# <a name="bad-file-name-or-number"></a>Numero o nome file errato
Si è verificato un errore durante il tentativo di accedere al file specificato. Tra le possibili cause di questo errore sono:  
  
- Un'istruzione fa riferimento a un file con un nome o un numero di file non specificato nell' `FileOpen` istruzione o che è stato specificato in un' `FileOpen` istruzione ma che è stato successivamente chiuso.  
  
- Un'istruzione fa riferimento a un file con un numero non compreso nell'intervallo di numeri di file.  
  
- Un'istruzione fa riferimento a un nome o a un numero di file non valido.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che il nome del file sia specificato in un' `FileOpen` istruzione. Si noti che se è stata richiamata l' `FileClose` istruzione senza argomenti, è possibile che tutti i file aperti siano stati chiusi inavvertitamente.  
  
2. Se il codice genera numeri di file algoritmicamente, verificare che i numeri siano validi.  
  
3. Controllare i nomi dei file per assicurarsi che siano conformi alle convenzioni del sistema operativo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Convenzioni di denominazione di Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
