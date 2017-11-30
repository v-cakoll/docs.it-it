---
title: Ottimizzazione per l'hosting Web condiviso
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a>Ottimizzazione per l'hosting Web condiviso
Se si è l'amministratore per un server condiviso che ospita più siti Web di piccole dimensioni, è possibile ottimizzare le prestazioni e aumentare la capacità del sito ad aggiungere le seguenti `gcTrimCommitOnLowMemory` impostazione il `runtime` nodo nel file Aspnet. config in .NET Directory:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  Questa impostazione è consigliata solo per il Web condiviso scenari di hosting.  
  
 Perché il garbage collector riserva memoria per le future allocazioni, lo spazio può essere maggiore di quello effettivamente necessario. È possibile ridurre i tempi di tale spazio quando è presente un carico pesante in memoria di sistema. La riduzione di tale spazio migliora le prestazioni e si espande la capacità di ospitare più siti.  
  
 Quando il `gcTrimCommitOnLowMemory` è attivata, il garbage collector valuta il carico di memoria di sistema e attiva la modalità trimming quando il carico raggiunge il 90%. La modalità di rimozione viene mantenuta fino a quando il carico scende sotto l'85%.  
  
 Quando le condizioni lo consentono, il garbage collector può decidere che la `gcTrimCommitOnLowMemory` impostazione non consentono l'applicazione corrente e Ignora.  
  
## <a name="example"></a>Esempio  
 Il frammento XML seguente viene illustrato come abilitare il `gcTrimCommitOnLowMemory` impostazione. Puntini di sospensione indicano altre impostazioni che verrebbero il `runtime` nodo.  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
