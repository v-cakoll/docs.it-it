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
ms.openlocfilehash: 830a65a4490b1d084e3bb301e89293ccb9424b32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33387003"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="6754b-102">MDA pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="6754b-102">pInvokeLog MDA</span></span>
<span data-ttu-id="6754b-103">L'assistente al debug gestito `pInvokeLog` viene attivato per ogni firma platform invoke univoca usata durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6754b-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="6754b-104">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="6754b-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="6754b-105">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="6754b-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="6754b-106">Output</span><span class="sxs-lookup"><span data-stu-id="6754b-106">Output</span></span>  
 <span data-ttu-id="6754b-107">Un messaggio che indica la firma platform invoke usata durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6754b-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="6754b-108">Configurazione</span><span class="sxs-lookup"><span data-stu-id="6754b-108">Configuration</span></span>  
 <span data-ttu-id="6754b-109">Ogni elemento match corrispondente filtra i file DLL per cui vengono effettuate chiamate di platform invoke.</span><span class="sxs-lookup"><span data-stu-id="6754b-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6754b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6754b-110">See Also</span></span>  
 [<span data-ttu-id="6754b-111">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="6754b-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="6754b-112">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="6754b-112">Consuming Unmanaged DLL Functions</span></span>](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)
