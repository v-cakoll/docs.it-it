---
title: '&#39;Riga&#39; istruzioni non sono più supportate (errore del compilatore Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 36226cc371ffb8a51cb8d0f918952f1c717aea10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702973"
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a>&#39;Riga&#39; istruzioni non sono più supportate (errore del compilatore Visual Basic)
Istruzioni a riga non sono più supportate. Funzionalità dei / o dei file è disponibile come `Microsoft.VisualBasic.FileSystem.LineInput` ed è disponibile come funzionalità grafiche `System.Drawing.Graphics.DrawLine`.  
  
 **ID errore:** BC30830  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Se si esegue l'accesso ai file, usare `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Per la grafica, usare `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.IO>
- <xref:System.Drawing>
- [Accesso ai file con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
