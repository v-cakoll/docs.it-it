---
title: MDA pInvokeLog
description: Comprendere l'assistente al debug gestito pInvokeLog, che viene attivato per ogni firma platform invoke univoca utilizzata durante l'esecuzione in .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: 05af4e17a91f7c0d8f3576a86d3d784ef6666aed
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803690"
---
# <a name="pinvokelog-mda"></a>MDA pInvokeLog
L'assistente al debug gestito `pInvokeLog` viene attivato per ogni firma platform invoke univoca usata durante l'esecuzione.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
 Un messaggio che indica la firma platform invoke usata durante l'esecuzione.  
  
## <a name="configuration"></a>Configurazione  
 Ogni elemento match corrispondente filtra i file DLL per cui vengono effettuate chiamate di platform invoke.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Utilizzo di funzioni di DLL non gestite](../interop/consuming-unmanaged-dll-functions.md)
