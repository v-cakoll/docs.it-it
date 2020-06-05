---
title: Le istruzioni 'Line' non sono più supportate (errore del compilatore Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: a3d243f39f3fc45ca6b1ba0d26892d4c3db56f59
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397298"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>Le istruzioni 'Line' non sono più supportate (errore del compilatore Visual Basic)
Le istruzioni line non sono più supportate. La funzionalità di I/O di file è disponibile come `Microsoft.VisualBasic.FileSystem.LineInput` e la funzionalità grafica è disponibile come `System.Drawing.Graphics.DrawLine` .  
  
 **ID errore:** BC30830  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Se si esegue l'accesso ai file, utilizzare `Microsoft.VisualBasic.FileSystem.LineInput` .  
  
2. Per la grafica, usare `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IO>
- <xref:System.Drawing>
- [Accesso ai file con Visual Basic](../../developing-apps/programming/drives-directories-files/file-access.md)
