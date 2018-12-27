---
title: Quando si usano argomenti di tipo 'Object', utilizzare 'FilePutObject' anziché 'FilePut'
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: df7d7c54992984bcb1684e41f60ae8361a3aed03
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2018
ms.locfileid: "53774225"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>Quando si usano argomenti di tipo 'Object', utilizzare 'FilePutObject' anziché 'FilePut'
Il metodo `FilePut` include un argomento di tipo `Object`. Per evitare ambiguità, è opportuno usare`FilePutObject` invece di `FilePut` .  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Sostituire `FilePut` con `FilePutObject`.  
  
-   Eseguire il cast dell'argomento `Object` su un tipo più specifico.  
  
-   Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vedere anche  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
