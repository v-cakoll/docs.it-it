---
title: MDA invalidMemberDeclaration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4f625cbc7d7c46eee5b2eb8d7e47d4a5754fc26
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="31bb7-102">MDA invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="31bb7-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="31bb7-103">L'assistente al debug gestito `invalidMemberDeclaration` viene attivato per segnalare un errore che si è verificato durante l'identificazione della modalità di marshalling dei parametri di un membro che deve essere chiamato da COM.</span><span class="sxs-lookup"><span data-stu-id="31bb7-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="31bb7-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="31bb7-104">Symptoms</span></span>  
 <span data-ttu-id="31bb7-105">A COM viene restituito un HRESULT di errore senza che sia stato chiamato il metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="31bb7-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="31bb7-106">Causa</span><span class="sxs-lookup"><span data-stu-id="31bb7-106">Cause</span></span>  
 <span data-ttu-id="31bb7-107">La causa più probabile è la presenza di un attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatibile in uno dei parametri.</span><span class="sxs-lookup"><span data-stu-id="31bb7-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="31bb7-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="31bb7-108">Resolution</span></span>  
 <span data-ttu-id="31bb7-109">Specificare attributi <xref:System.Runtime.InteropServices.MarshalAsAttribute> validi nei parametri.</span><span class="sxs-lookup"><span data-stu-id="31bb7-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="31bb7-110">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="31bb7-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="31bb7-111">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="31bb7-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="31bb7-112">Output</span><span class="sxs-lookup"><span data-stu-id="31bb7-112">Output</span></span>  
 <span data-ttu-id="31bb7-113">Un messaggio informativo che contiene il nome del membro, il nome del tipo e il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="31bb7-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="31bb7-114">Configurazione</span><span class="sxs-lookup"><span data-stu-id="31bb7-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="31bb7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31bb7-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="31bb7-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="31bb7-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="31bb7-117">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="31bb7-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
