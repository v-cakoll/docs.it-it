---
title: Le istruzioni 'Line' non sono più supportate (errore del compilatore Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: c7a3e6bcd0db268a0e0acfc74c570e26f89cff6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921069"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="b6086-102">Le istruzioni 'Line' non sono più supportate (errore del compilatore Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6086-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="b6086-103">Istruzioni a riga non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="b6086-103">Line statements are no longer supported.</span></span> <span data-ttu-id="b6086-104">Funzionalità dei / o dei file è disponibile come `Microsoft.VisualBasic.FileSystem.LineInput` ed è disponibile come funzionalità grafiche `System.Drawing.Graphics.DrawLine`.</span><span class="sxs-lookup"><span data-stu-id="b6086-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="b6086-105">**ID errore:** BC30830</span><span class="sxs-lookup"><span data-stu-id="b6086-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b6086-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b6086-106">To correct this error</span></span>  
  
1. <span data-ttu-id="b6086-107">Se si esegue l'accesso ai file, usare `Microsoft.VisualBasic.FileSystem.LineInput`.</span><span class="sxs-lookup"><span data-stu-id="b6086-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2. <span data-ttu-id="b6086-108">Per la grafica, usare `System.Drawing.Graphics.Drawline`.</span><span class="sxs-lookup"><span data-stu-id="b6086-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6086-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6086-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="b6086-110">Accesso ai file con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6086-110">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
