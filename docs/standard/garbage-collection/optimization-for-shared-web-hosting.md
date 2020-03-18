---
title: Ottimizzazione per l'hosting Web condiviso
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
ms.openlocfilehash: 07a100e2cd6aaff2b54b99144c9d762c8979fb47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140276"
---
# <a name="optimization-for-shared-web-hosting"></a>Ottimizzazione per l'hosting Web condiviso
L'amministratore di un server condiviso che ospita più siti Web di piccole dimensioni può ottimizzare le prestazioni e aumentare la capacità del sito aggiungendo l'impostazione `gcTrimCommitOnLowMemory` seguente al nodo `runtime` nel file Aspnet.config nella directory .NET:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
> Questa impostazione è consigliata solo per scenari di hosting Web condivisi.  
  
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

- [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
