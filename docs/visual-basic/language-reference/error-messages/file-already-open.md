---
title: File già aperto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: cda72e03eb5c2469b8106957a0c50fbfa5314549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567035"
---
# <a name="file-already-open"></a>File già aperto
In alcuni casi un file deve essere chiuso prima di un altro `FileOpen` o può verificarsi un'altra operazione. Di seguito sono riportate le cause possibili dell'errore:  
  
-   Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto  
  
-   Un'istruzione fa riferimento a un file aperto.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Chiudere il file prima di eseguire l'istruzione.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
