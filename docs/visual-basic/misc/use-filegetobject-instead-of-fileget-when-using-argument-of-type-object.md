---
title: Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: ddbe187ed1210d238448a5ff3feaee18beea1def
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2018
ms.locfileid: "53768011"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'
Il metodo `FileGet` include un argomento di tipo `Object`. Per evitare ambiguità, è opportuno usare`FileGetObject` invece di `FileGet` .  
  
 Si noti che la funzionalità offerta da `My.Computer.Filesystem` garantisce una maggiore facilità d'uso e prestazioni superiori sia rispetto a `FileGet` che a `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Sostituire `FileGet` con `FileGetObject`.  
  
2.  Eseguire il cast dell'argomento `Object` su un tipo più specifico.  
  
## <a name="see-also"></a>Vedere anche  
   
 [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
