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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7525ca263449da77b4b6364fd6bcfd51dcba145d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="optimization-for-shared-web-hosting"></a>Ottimizzazione per l'hosting Web condiviso
L'amministratore di un server condiviso che ospita più siti Web di piccole dimensioni può ottimizzare le prestazioni e aumentare la capacità del sito aggiungendo l'impostazione `gcTrimCommitOnLowMemory` seguente al nodo `runtime` nel file Aspnet.config nella directory .NET:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  Questa impostazione è consigliata solo per scenari di hosting Web condivisi.  
  
 Dato che il Garbage Collector riserva memoria per le allocazioni future, lo spazio di cui viene eseguito il commit può essere maggiore di quello strettamente necessario. È possibile ridurre questo spazio per gestire i momenti in cui è presente un carico pesante sulla memoria di sistema. La riduzione di questo spazio migliora le prestazioni e aumenta la capacità di ospitare più siti.  
  
 Quando l'impostazione `gcTrimCommitOnLowMemory` è abilitata, il Garbage Collector valuta il carico di memoria di sistema e attiva la modalità trimming quando il carico raggiunge il 90%. La modalità trimming viene mantenuta fino a quando il carico non scende sotto l'85%.  
  
 Quando le condizioni lo consentono, il Garbage Collector può decidere che l'impostazione `gcTrimCommitOnLowMemory` non sarà utile per l'applicazione corrente e ignorarla.  
  
## <a name="example"></a>Esempio  
 Il frammento XML seguente mostra come abilitare l'impostazione `gcTrimCommitOnLowMemory`. I puntini di sospensione indicano altre impostazioni che sarebbero disponibili nel nodo `runtime`.  
  
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
