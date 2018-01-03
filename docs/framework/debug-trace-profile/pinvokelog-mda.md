---
title: MDA pInvokeLog
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 343ec424105d1c775592aba316b50da4010f7c8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="4799d-102">MDA pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="4799d-102">pInvokeLog MDA</span></span>
<span data-ttu-id="4799d-103">L'assistente al debug gestito `pInvokeLog` viene attivato per ogni firma platform invoke univoca usata durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4799d-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="4799d-104">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="4799d-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="4799d-105">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="4799d-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="4799d-106">Output</span><span class="sxs-lookup"><span data-stu-id="4799d-106">Output</span></span>  
 <span data-ttu-id="4799d-107">Un messaggio che indica la firma platform invoke usata durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4799d-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="4799d-108">Configurazione</span><span class="sxs-lookup"><span data-stu-id="4799d-108">Configuration</span></span>  
 <span data-ttu-id="4799d-109">Ogni elemento match corrispondente filtra i file DLL per cui vengono effettuate chiamate di platform invoke.</span><span class="sxs-lookup"><span data-stu-id="4799d-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4799d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4799d-110">See Also</span></span>  
 [<span data-ttu-id="4799d-111">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="4799d-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="4799d-112">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="4799d-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
