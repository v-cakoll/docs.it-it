---
title: "File già aperto"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3305831e840510e3f0b5bcb8bf847e39ea3ee4ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="file-already-open"></a>File già aperto
In alcuni casi un file deve essere chiusi prima di un altro `FileOpen` oppure può avvenire in un'altra operazione. Di seguito sono riportate le cause possibili dell'errore:  
  
-   Modalità output sequenziale `FileOpen` operazione è stata eseguita per un file che è già aperto  
  
-   Un'istruzione fa riferimento a un file aperto.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Chiudere il file prima di eseguire l'istruzione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
