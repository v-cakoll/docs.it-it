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
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="5f647-102">Il file è troppo grande per essere letto in una matrice byte</span><span class="sxs-lookup"><span data-stu-id="5f647-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="5f647-103">La dimensione del file che si sta tentando di leggere in una matrice di byte supera i 4 GB.</span><span class="sxs-lookup"><span data-stu-id="5f647-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="5f647-104">Il `My.Computer.FileSystem.ReadAllBytes` metodo non è in grado di leggere un file che supera questa dimensione.</span><span class="sxs-lookup"><span data-stu-id="5f647-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f647-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5f647-105">To correct this error</span></span>  
  
- <span data-ttu-id="5f647-106">Usare un <xref:System.IO.StreamReader> per leggere il file.</span><span class="sxs-lookup"><span data-stu-id="5f647-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="5f647-107">Per ulteriori informazioni, vedere [nozioni di base sull'i/O dei file .NET Framework e sul file System (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span><span class="sxs-lookup"><span data-stu-id="5f647-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f647-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f647-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="5f647-109">Accesso ai file con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f647-109">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="5f647-110">Procedura: Leggere il testo da file con un oggetto StreamReader</span><span class="sxs-lookup"><span data-stu-id="5f647-110">How to: Read Text from Files with a StreamReader</span></span>](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
