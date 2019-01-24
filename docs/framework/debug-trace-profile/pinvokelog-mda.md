---
title: MDA pInvokeLog
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe1d783017369a78074e5abf278ac2facf6ee32b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734065"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="e4c73-102">MDA pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="e4c73-102">pInvokeLog MDA</span></span>
<span data-ttu-id="e4c73-103">L'assistente al debug gestito `pInvokeLog` viene attivato per ogni firma platform invoke univoca usata durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e4c73-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="e4c73-104">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="e4c73-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="e4c73-105">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="e4c73-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="e4c73-106">Output</span><span class="sxs-lookup"><span data-stu-id="e4c73-106">Output</span></span>  
 <span data-ttu-id="e4c73-107">Un messaggio che indica la firma platform invoke usata durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e4c73-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e4c73-108">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e4c73-108">Configuration</span></span>  
 <span data-ttu-id="e4c73-109">Ogni elemento match corrispondente filtra i file DLL per cui vengono effettuate chiamate di platform invoke.</span><span class="sxs-lookup"><span data-stu-id="e4c73-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e4c73-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4c73-110">See also</span></span>
- [<span data-ttu-id="e4c73-111">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="e4c73-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e4c73-112">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="e4c73-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
