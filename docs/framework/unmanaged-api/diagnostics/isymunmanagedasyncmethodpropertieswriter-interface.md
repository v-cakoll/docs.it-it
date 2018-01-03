---
title: Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99d61fdb9f7e3eb2bc10de7584061d8922bf9285
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="d045d-102">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="d045d-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="d045d-103">Consente di definire le informazioni sul metodo async facoltativo per ogni simbolo del metodo.</span><span class="sxs-lookup"><span data-stu-id="d045d-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="d045d-104">Utilizzare sempre con un metodo di aperto. vale a dire, tra le chiamate al [OpenMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) e [CloseMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="d045d-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d045d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d045d-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="d045d-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="d045d-106">Methods</span></span>  
 <span data-ttu-id="d045d-107">Per l'interfaccia sono disponibili i seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="d045d-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="d045d-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="d045d-108">Method</span></span>|<span data-ttu-id="d045d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d045d-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d045d-110">Metodo DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="d045d-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="d045d-111">Definire un gruppo di async await operazioni nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="d045d-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="d045d-112">Istruzione return di un await, che identifica un potenziale rendimento corrisponde a ogni offset yield.</span><span class="sxs-lookup"><span data-stu-id="d045d-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="d045d-113">Ogni `breakpointMethod` / `breakpointOffset` coppia identifica dove riprende l'operazione asincrona, potrebbe essere in un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="d045d-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="d045d-114">Metodo DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="d045d-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="d045d-115">Imposta l'offset per il gestore catch generato dal compilatore che esegue il wrapping di un metodo asincrono IL.</span><span class="sxs-lookup"><span data-stu-id="d045d-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="d045d-116">Offset IL di catch generato viene utilizzata dal debugger per gestire catch come se fosse il codice non utente, anche se può verificarsi in un metodo del codice utente.</span><span class="sxs-lookup"><span data-stu-id="d045d-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="d045d-117">In particolare, viene utilizzato in risposta a un **CatchHandlerFound** evento dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d045d-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="d045d-118">Metodo DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="d045d-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="d045d-119">Imposta il metodo di avvio che avvia l'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="d045d-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d045d-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d045d-120">Requirements</span></span>  
 <span data-ttu-id="d045d-121">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d045d-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d045d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d045d-122">See Also</span></span>  
 [<span data-ttu-id="d045d-123">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="d045d-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
