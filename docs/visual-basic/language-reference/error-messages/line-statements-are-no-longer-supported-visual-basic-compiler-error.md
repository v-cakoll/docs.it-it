---
title: Le istruzioni 'Line' non sono più supportate (errore del compilatore Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 7616bcdc39ab479049586534fac22f1e2d96a700
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831839"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>Le istruzioni 'Line' non sono più supportate (errore del compilatore Visual Basic)
Istruzioni a riga non sono più supportate. Funzionalità dei / o dei file è disponibile come `Microsoft.VisualBasic.FileSystem.LineInput` ed è disponibile come funzionalità grafiche `System.Drawing.Graphics.DrawLine`.  
  
 **ID errore:** BC30830  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Se si esegue l'accesso ai file, usare `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Per la grafica, usare `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO>
- <xref:System.Drawing>
- [Accesso ai file con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
