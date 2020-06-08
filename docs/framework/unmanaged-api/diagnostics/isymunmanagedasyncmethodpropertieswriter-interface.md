---
title: Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 04876483fd42e3f6e55222416fd0747891734a52
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501859"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="25cf6-102">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="25cf6-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="25cf6-103">Consente di definire informazioni facoltative sul metodo asincrono per ogni simbolo di metodo.</span><span class="sxs-lookup"><span data-stu-id="25cf6-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="25cf6-104">Usare sempre con un metodo aperto; ovvero tra le chiamate al [Metodo OpenMethod](isymunmanagedwriter-openmethod-method.md) e il [Metodo CloseMethod](isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="25cf6-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25cf6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25cf6-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="25cf6-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="25cf6-106">Methods</span></span>  
 <span data-ttu-id="25cf6-107">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="25cf6-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="25cf6-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="25cf6-108">Method</span></span>|<span data-ttu-id="25cf6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25cf6-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25cf6-110">Metodo DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="25cf6-110">DefineAsyncStepInfo Method</span></span>](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="25cf6-111">Definire un gruppo di operazioni di attesa asincrone nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="25cf6-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="25cf6-112">Ogni offset yield corrisponde a un'istruzione return di await, che identifica un potenziale rendimento.</span><span class="sxs-lookup"><span data-stu-id="25cf6-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="25cf6-113">Ogni `breakpointMethod` / `breakpointOffset` coppia identifica la posizione in cui verrà ripresa l'operazione asincrona. potrebbe trovarsi in un metodo diverso.</span><span class="sxs-lookup"><span data-stu-id="25cf6-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="25cf6-114">Metodo DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="25cf6-114">DefineCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="25cf6-115">Imposta l'offset il per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono.</span><span class="sxs-lookup"><span data-stu-id="25cf6-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="25cf6-116">L'offset il dell'oggetto catch generato viene utilizzato dal debugger per gestire l'oggetto Catch come se fosse un codice non utente, anche se potrebbe verificarsi in un metodo del codice utente.</span><span class="sxs-lookup"><span data-stu-id="25cf6-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="25cf6-117">In particolare, viene usato in risposta a un evento di eccezione **CatchHandlerFound** .</span><span class="sxs-lookup"><span data-stu-id="25cf6-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="25cf6-118">Metodo DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="25cf6-118">DefineKickoffMethod Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="25cf6-119">Imposta il metodo iniziale che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="25cf6-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25cf6-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25cf6-120">Requirements</span></span>  
 <span data-ttu-id="25cf6-121">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="25cf6-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25cf6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25cf6-122">See also</span></span>

- [<span data-ttu-id="25cf6-123">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="25cf6-123">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
