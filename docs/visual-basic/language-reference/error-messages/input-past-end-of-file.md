---
title: Input oltre la fine del file
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 5da14c7a28ecdcd023fc6439cb6ed64444c1183b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768553"
---
# <a name="input-past-end-of-file"></a>Input oltre la fine del file
Entrambi un `Input` istruzione sta leggendo da un file vuoto o uno in cui tutti i dati viene utilizzato o è stato usato il `EOF` funzione con un file aperto per l'accesso binario.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Usare la `EOF` funzione immediatamente prima di `Input` istruzione per rilevare la fine del file.  
  
2. Se il file viene aperto per l'accesso binario, usare `Seek` e `Loc`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
