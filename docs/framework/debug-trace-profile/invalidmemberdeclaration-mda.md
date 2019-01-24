---
title: MDA invalidMemberDeclaration
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c276df65497a0d8cafea80959b8193790c19ebba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667349"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="8d0b0-102">MDA invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="8d0b0-102">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="8d0b0-103">L'assistente al debug gestito `invalidMemberDeclaration` viene attivato per segnalare un errore che si è verificato durante l'identificazione della modalità di marshalling dei parametri di un membro che deve essere chiamato da COM.</span><span class="sxs-lookup"><span data-stu-id="8d0b0-103">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8d0b0-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="8d0b0-104">Symptoms</span></span>  
 <span data-ttu-id="8d0b0-105">A COM viene restituito un HRESULT di errore senza che sia stato chiamato il metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="8d0b0-105">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8d0b0-106">Causa</span><span class="sxs-lookup"><span data-stu-id="8d0b0-106">Cause</span></span>  
 <span data-ttu-id="8d0b0-107">La causa più probabile è la presenza di un attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatibile in uno dei parametri.</span><span class="sxs-lookup"><span data-stu-id="8d0b0-107">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8d0b0-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="8d0b0-108">Resolution</span></span>  
 <span data-ttu-id="8d0b0-109">Specificare attributi <xref:System.Runtime.InteropServices.MarshalAsAttribute> validi nei parametri.</span><span class="sxs-lookup"><span data-stu-id="8d0b0-109">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8d0b0-110">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="8d0b0-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="8d0b0-111">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="8d0b0-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8d0b0-112">Output</span><span class="sxs-lookup"><span data-stu-id="8d0b0-112">Output</span></span>  
 <span data-ttu-id="8d0b0-113">Un messaggio informativo che contiene il nome del membro, il nome del tipo e il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="8d0b0-113">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8d0b0-114">Configurazione</span><span class="sxs-lookup"><span data-stu-id="8d0b0-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d0b0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d0b0-115">See also</span></span>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8d0b0-116">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="8d0b0-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8d0b0-117">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="8d0b0-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
