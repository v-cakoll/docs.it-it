---
title: Usa &#39; FileGetObject &#39; invece di &#39; FileGet &#39; Quando si usano argomenti di tipo &#39; oggetto &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c5be466a8a0339bdb57818755d85a26d632d774
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a>Usa &#39; FileGetObject &#39; invece di &#39; FileGet &#39; Quando si usano argomenti di tipo &#39; oggetto &#39;
Il metodo `FileGet` include un argomento di tipo `Object`. Per evitare ambiguità, è opportuno usare`FileGetObject` invece di `FileGet` .  
  
 Si noti che la funzionalità offerta da `My.Computer.Filesystem` garantisce una maggiore facilità d'uso e prestazioni superiori sia rispetto a `FileGet` che a `FileGetObject`.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Sostituire `FileGet` con `FileGetObject`.  
  
2.  Eseguire il cast dell'argomento `Object` su un tipo più specifico.  
  
## <a name="see-also"></a>Vedere anche  
   
 [FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
