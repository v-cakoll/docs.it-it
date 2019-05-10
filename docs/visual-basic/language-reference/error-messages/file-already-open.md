---
title: File già aperto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 8ec878e04b0128c997c5be51d2c714d55abcde8c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665125"
---
# <a name="file-already-open"></a><span data-ttu-id="a1230-102">File già aperto</span><span class="sxs-lookup"><span data-stu-id="a1230-102">File already open</span></span>
<span data-ttu-id="a1230-103">In alcuni casi un file deve essere chiuso prima di un altro `FileOpen` o può verificarsi un'altra operazione.</span><span class="sxs-lookup"><span data-stu-id="a1230-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="a1230-104">Di seguito sono riportate le cause possibili dell'errore:</span><span class="sxs-lookup"><span data-stu-id="a1230-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="a1230-105">Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto</span><span class="sxs-lookup"><span data-stu-id="a1230-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="a1230-106">Un'istruzione fa riferimento a un file aperto.</span><span class="sxs-lookup"><span data-stu-id="a1230-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a1230-107">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="a1230-107">To correct this error</span></span>  
  
1. <span data-ttu-id="a1230-108">Chiudere il file prima di eseguire l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="a1230-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1230-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1230-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
