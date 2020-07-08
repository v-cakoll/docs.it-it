---
title: MDA invalidMemberDeclaration
description: Esaminare l'assistente al debug gestito invalidMemberDeclaration, che viene richiamato se un HRESULT di errore viene restituito a COM senza chiamare il metodo gestito.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: 5dbfba2baec3263d91746c06379438e97a81f005
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051714"
---
# <a name="invalidmemberdeclaration-mda"></a><span data-ttu-id="0b1d5-103">MDA invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="0b1d5-103">invalidMemberDeclaration MDA</span></span>
<span data-ttu-id="0b1d5-104">L'assistente al debug gestito `invalidMemberDeclaration` viene attivato per segnalare un errore che si è verificato durante l'identificazione della modalità di marshalling dei parametri di un membro che deve essere chiamato da COM.</span><span class="sxs-lookup"><span data-stu-id="0b1d5-104">The `invalidMemberDeclaration` managed debugging assistant (MDA) is activated to report an error that occurs while determining how to marshal the parameters of a member to be called from COM.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="0b1d5-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="0b1d5-105">Symptoms</span></span>  
 <span data-ttu-id="0b1d5-106">A COM viene restituito un HRESULT di errore senza che sia stato chiamato il metodo gestito.</span><span class="sxs-lookup"><span data-stu-id="0b1d5-106">A failure HRESULT is returned to COM without the managed method having been called.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="0b1d5-107">Causa</span><span class="sxs-lookup"><span data-stu-id="0b1d5-107">Cause</span></span>  
 <span data-ttu-id="0b1d5-108">La causa più probabile è la presenza di un attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> incompatibile in uno dei parametri.</span><span class="sxs-lookup"><span data-stu-id="0b1d5-108">This is most likely due to an incompatible <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute on one of the parameters.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="0b1d5-109">Soluzione</span><span class="sxs-lookup"><span data-stu-id="0b1d5-109">Resolution</span></span>  
 <span data-ttu-id="0b1d5-110">Specificare attributi <xref:System.Runtime.InteropServices.MarshalAsAttribute> validi nei parametri.</span><span class="sxs-lookup"><span data-stu-id="0b1d5-110">Specify valid <xref:System.Runtime.InteropServices.MarshalAsAttribute> attributes on the parameters.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="0b1d5-111">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="0b1d5-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="0b1d5-112">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="0b1d5-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="0b1d5-113">Output</span><span class="sxs-lookup"><span data-stu-id="0b1d5-113">Output</span></span>  
 <span data-ttu-id="0b1d5-114">Un messaggio informativo che contiene il nome del membro, il nome del tipo e il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="0b1d5-114">An informational message containing the member name, type name, and error message.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="0b1d5-115">Configurazione</span><span class="sxs-lookup"><span data-stu-id="0b1d5-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b1d5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b1d5-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="0b1d5-117">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="0b1d5-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="0b1d5-118">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="0b1d5-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
