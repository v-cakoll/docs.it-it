---
title: Il file è troppo grande per essere letto in una matrice byte
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 1b04d47cab77269a0ce84ef77c162a4401d99d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Il file è troppo grande per essere letto in una matrice byte
Le dimensioni del file di cui che si sta tentando di leggere in una matrice di byte superano i 4 GB. Il `My.Computer.FileSystem.ReadAllBytes` (metodo) non è possibile leggere un file che supera questa dimensione.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Utilizzare un <xref:System.IO.StreamReader> per leggere il file. Per ulteriori informazioni, vedere [nozioni di base di .NET Framework i/o File e il File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [Accesso ai file con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [Procedura: leggere il testo da file con un oggetto StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
