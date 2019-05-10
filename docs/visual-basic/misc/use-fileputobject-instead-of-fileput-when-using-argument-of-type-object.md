---
title: Quando si usano argomenti di tipo 'Object', utilizzare 'FilePutObject' anziché 'FilePut'
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: bf1f50d0d8eb9b0b8518075b0e48f40645a02a25
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913218"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>Quando si usano argomenti di tipo 'Object', utilizzare 'FilePutObject' anziché 'FilePut'
Il metodo `FilePut` include un argomento di tipo `Object`. Per evitare ambiguità, è opportuno usare`FilePutObject` invece di `FilePut` .  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Sostituire `FilePut` con `FilePutObject`.  
  
- Eseguire il cast dell'argomento `Object` su un tipo più specifico.  
  
- Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vedere anche

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
