---
title: Il file è troppo grande per essere letto in una matrice byte
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: b81fc9332d5f1347404fcdd73bce72b6b09778b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363124"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Il file è troppo grande per essere letto in una matrice byte
La dimensione del file che si sta tentando di leggere in una matrice di byte supera i 4 GB. Il `My.Computer.FileSystem.ReadAllBytes` metodo non è in grado di leggere un file che supera questa dimensione.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Usare un <xref:System.IO.StreamReader> per leggere il file. Per ulteriori informazioni, vedere [nozioni di base sull'i/O dei file .NET Framework e sul file System (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [Accesso ai file con Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
- [Procedura: Leggere il testo da file con un oggetto StreamReader](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
