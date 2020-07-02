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
# <a name="pinvokelog-mda"></a><span data-ttu-id="a644e-103">MDA pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="a644e-103">pInvokeLog MDA</span></span>
<span data-ttu-id="a644e-104">L'assistente al debug gestito `pInvokeLog` viene attivato per ogni firma platform invoke univoca usata durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a644e-104">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a644e-105">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="a644e-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="a644e-106">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="a644e-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a644e-107">Output</span><span class="sxs-lookup"><span data-stu-id="a644e-107">Output</span></span>  
 <span data-ttu-id="a644e-108">Un messaggio che indica la firma platform invoke usata durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a644e-108">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a644e-109">Configurazione</span><span class="sxs-lookup"><span data-stu-id="a644e-109">Configuration</span></span>  
 <span data-ttu-id="a644e-110">Ogni elemento match corrispondente filtra i file DLL per cui vengono effettuate chiamate di platform invoke.</span><span class="sxs-lookup"><span data-stu-id="a644e-110">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a644e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a644e-111">See also</span></span>

- [<span data-ttu-id="a644e-112">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="a644e-112">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a644e-113">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="a644e-113">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
