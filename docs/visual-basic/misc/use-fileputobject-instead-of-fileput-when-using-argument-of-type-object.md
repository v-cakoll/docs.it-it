---
title: Utilizzare &#39;FilePutObject&#39; anziché &#39;FilePut&#39; quando si usano argomenti di tipo &#39;oggetto&#39;
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 529352d98c175981c20861205ce04c8a2ebcdca9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a>Utilizzare &#39;FilePutObject&#39; anziché &#39;FilePut&#39; quando si usano argomenti di tipo &#39;oggetto&#39;
Il `FilePut` metodo include un argomento di tipo `Object`. Per evitare ambiguità, è opportuno usare`FilePutObject` invece di `FilePut` .  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Sostituire `FilePut` con `FilePutObject`.  
  
-   Eseguire il cast dell'argomento `Object` su un tipo più specifico.  
  
-   Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vedere anche  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
