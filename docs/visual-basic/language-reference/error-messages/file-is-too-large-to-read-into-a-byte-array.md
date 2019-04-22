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
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="80289-102">Il file è troppo grande per essere letto in una matrice byte</span><span class="sxs-lookup"><span data-stu-id="80289-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="80289-103">Le dimensioni del file di cui che si sta tentando di leggere in una matrice di byte superano i 4 GB.</span><span class="sxs-lookup"><span data-stu-id="80289-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="80289-104">Il `My.Computer.FileSystem.ReadAllBytes` (metodo) non è possibile leggere un file che supera la dimensione specificata.</span><span class="sxs-lookup"><span data-stu-id="80289-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80289-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="80289-105">To correct this error</span></span>  
  
-   <span data-ttu-id="80289-106">Usare un <xref:System.IO.StreamReader> per leggere il file.</span><span class="sxs-lookup"><span data-stu-id="80289-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="80289-107">Per altre informazioni, vedere [nozioni di base di .NET Framework File i/o e il File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span><span class="sxs-lookup"><span data-stu-id="80289-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80289-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80289-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="80289-109">Accesso ai file con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80289-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="80289-110">Procedura: Leggere il testo da file con un oggetto StreamReader</span><span class="sxs-lookup"><span data-stu-id="80289-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
