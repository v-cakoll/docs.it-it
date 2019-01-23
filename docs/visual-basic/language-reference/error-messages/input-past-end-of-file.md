---
title: Input oltre la fine del file
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 29a9b5ce3c3f8e6a02b52beda1338fd699143570
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491337"
---
# <a name="input-past-end-of-file"></a>Input oltre la fine del file
Entrambi un `Input` istruzione sta leggendo da un file vuoto o uno in cui tutti i dati viene utilizzato o è stato usato il `EOF` funzione con un file aperto per l'accesso binario.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Usare la `EOF` funzione immediatamente prima di `Input` istruzione per rilevare la fine del file.  
  
2.  Se il file viene aperto per l'accesso binario, usare `Seek` e `Loc`.  
  
## <a name="see-also"></a>Vedere anche
- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
