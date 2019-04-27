---
title: File già aperto
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802648"
---
# <a name="file-already-open"></a>File già aperto
In alcuni casi un file deve essere chiuso prima di un altro `FileOpen` o può verificarsi un'altra operazione. Di seguito sono riportate le cause possibili dell'errore:  
  
-   Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto  
  
-   Un'istruzione fa riferimento a un file aperto.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Chiudere il file prima di eseguire l'istruzione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
