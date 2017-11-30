---
title: Input oltre la fine del file
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27de462d5d28ee09107d75afe8269e7401c4dc39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="input-past-end-of-file"></a>Input oltre la fine del file
Entrambi un `Input` istruzione sta leggendo da un file che è vuoto o uno in cui tutti i dati vengono utilizzati, o è stato utilizzato il `EOF` funzione con un file aperto per l'accesso binario.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Utilizzare il `EOF` funzione immediatamente prima di `Input` istruzione per individuare la fine del file.  
  
2.  Se il file è aperto per l'accesso binario, utilizzare `Seek` e `Loc`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
