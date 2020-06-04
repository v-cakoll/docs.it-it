---
title: Errore di accesso al percorso/file
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: dfe96cd6eaa673438849fe8f799d46fa2617bfdd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387257"
---
# <a name="pathfile-access-error"></a>Errore di accesso al percorso/file
Durante un'operazione di accesso ai file o di accesso al disco, il sistema operativo non è in grado di effettuare una connessione tra il percorso e il nome del file.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che la specifica del file sia formattata correttamente. Un nome file può contenere un percorso completo (assoluto) o relativo. Un percorso completo inizia con il nome dell'unità (se il percorso si trova in un'altra unità) ed elenca il percorso esplicito dalla radice al file. Qualsiasi percorso non completo è relativo all'unità e alla directory correnti.  
  
2. Assicurarsi di non aver tentato di salvare un file che sostituirebbe un file di sola lettura esistente. In tal caso, modificare l'attributo di sola lettura del file di destinazione oppure salvare il file con un nome di file diverso.  
  
3. Assicurarsi che non si sia tentato di aprire un file di sola lettura in modalità sequenziale `Output` o `Append` . In tal caso, aprire il file in `Input` modalità o modificare l'attributo di sola lettura del file.  
  
4. Assicurarsi che non sia stato effettuato un tentativo di modifica di un progetto di Visual Basic all'interno di un database o di un documento.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di errore](../../programming-guide/language-features/error-types.md)
