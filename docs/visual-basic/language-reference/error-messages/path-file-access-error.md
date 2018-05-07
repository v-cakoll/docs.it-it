---
title: Errore di accesso percorso File
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 83ce8615b173a6f5835347ebc561a793655ec8f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="pathfile-access-error"></a>Errore di accesso al percorso/file
Durante un'operazione di accesso ai file o l'accesso al disco, il sistema operativo non può stabilire una connessione tra il percorso e il nome del file.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Verificare che la specifica del file è formattata correttamente. Un nome di file può contenere un nome completo (assoluto) o il relativo percorso. Il percorso completo inizia con il nome dell'unità (se il percorso in un'altra unità) ed elenca il percorso dalla radice esplicito al file. Qualsiasi percorso che non è completo è relativo unità corrente e la directory.  
  
2.  Assicurarsi che non si ha provato a salvare un file che sostituirà un file di sola lettura esistente. In questo caso, modificare l'attributo di sola lettura del file di destinazione o salvare il file con un nome file diverso.  
  
3.  Assicurarsi che si non tenta di aprire un file di sola lettura in sequenziale `Output` o `Append` modalità. In questo caso, aprire il file in `Input` modalità o modificare l'attributo di sola lettura del file.  
  
4.  Assicurarsi che non si ha provato a modificare un progetto di Visual Basic all'interno di un database o un documento.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)
