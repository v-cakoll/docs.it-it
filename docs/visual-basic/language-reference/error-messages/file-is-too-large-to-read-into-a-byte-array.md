---
title: "Il file è troppo grande per essere letto in una matrice byte"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bbdb5a4dcaa22ca84428ef28c8838a6d9a0ee1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
