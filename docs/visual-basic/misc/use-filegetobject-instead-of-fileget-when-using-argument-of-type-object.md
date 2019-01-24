---
title: Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 60eaabc686070aced908116728f06d4e82b5cecb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723394"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a>Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'
Il metodo `FileGet` include un argomento di tipo `Object`. Per evitare ambiguità, è opportuno usare`FileGetObject` invece di `FileGet` .  
  
 Si noti che la funzionalità offerta da `My.Computer.Filesystem` garantisce una maggiore facilità d'uso e prestazioni superiori sia rispetto a `FileGet` che a `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Sostituire `FileGet` con `FileGetObject`.  
  
2.  Eseguire il cast dell'argomento `Object` su un tipo più specifico.  
  
## <a name="see-also"></a>Vedere anche

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
