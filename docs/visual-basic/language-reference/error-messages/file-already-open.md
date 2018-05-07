---
title: File già aperto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 75a08b411a4afd7ea8e11953f1d465b082faa712
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="file-already-open"></a>File già aperto
In alcuni casi un file deve essere chiusi prima di un altro `FileOpen` oppure può avvenire in un'altra operazione. Di seguito sono riportate le cause possibili dell'errore:  
  
-   Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto  
  
-   Un'istruzione fa riferimento a un file aperto.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Chiudere il file prima di eseguire l'istruzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
