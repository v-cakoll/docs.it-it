---
title: Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: fdad64a4b35aa792c996d25a9fd72a9ce1126fbd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022545"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'
Il metodo `FileGet` include un argomento di tipo `Object`. Per evitare ambiguità, è opportuno usare`FileGetObject` invece di `FileGet` .  
  
 Si noti che la funzionalità offerta da `My.Computer.Filesystem` garantisce una maggiore facilità d'uso e prestazioni superiori sia rispetto a `FileGet` che a `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Sostituire `FileGet` con `FileGetObject`.  
  
2. Eseguire il cast dell'argomento `Object` su un tipo più specifico.  
  
## <a name="see-also"></a>Vedere anche

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
