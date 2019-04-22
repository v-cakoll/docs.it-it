---
title: Il file è troppo grande per essere letto in una matrice byte
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 0c7d35e08eeb42e35c4c40e47434a64393d829b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831514"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Il file è troppo grande per essere letto in una matrice byte
Le dimensioni del file di cui che si sta tentando di leggere in una matrice di byte superano i 4 GB. Il `My.Computer.FileSystem.ReadAllBytes` (metodo) non è possibile leggere un file che supera la dimensione specificata.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Usare un <xref:System.IO.StreamReader> per leggere il file. Per altre informazioni, vedere [nozioni di base di .NET Framework File i/o e il File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [Accesso ai file con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [Procedura: Leggere il testo da file con un oggetto StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
