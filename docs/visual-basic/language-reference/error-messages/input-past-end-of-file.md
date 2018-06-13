---
title: Input oltre la fine del file
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: abd5f5c6e5df262d1deadd74f0a146a8d436ceb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586741"
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
