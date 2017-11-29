---
title: Interfaccia ICorDebugNativeFrame2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2
helpviewer_keywords: ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c33eaa36313f0cf6aae904761fb40bb2dbf9d753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="5a716-102">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="5a716-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="5a716-103">Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="5a716-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a716-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5a716-104">Methods</span></span>  
  
|<span data-ttu-id="5a716-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5a716-105">Method</span></span>|<span data-ttu-id="5a716-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a716-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a716-107">IsChild (metodo)</span><span class="sxs-lookup"><span data-stu-id="5a716-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="5a716-108">Determina se il frame corrente è un frame figlio.</span><span class="sxs-lookup"><span data-stu-id="5a716-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="5a716-109">IsMatchingParentFrame (metodo)</span><span class="sxs-lookup"><span data-stu-id="5a716-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="5a716-110">Determina se l'intervallo specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="5a716-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="5a716-111">GetStackParameterSize (metodo)</span><span class="sxs-lookup"><span data-stu-id="5a716-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="5a716-112">Restituisce la dimensione complessiva dei parametri nello stack su sistemi operativi x86.</span><span class="sxs-lookup"><span data-stu-id="5a716-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a716-113">Note</span><span class="sxs-lookup"><span data-stu-id="5a716-113">Remarks</span></span>  
 <span data-ttu-id="5a716-114">Questa interfaccia estende logicamente l'interfaccia "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="5a716-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a716-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="5a716-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a716-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a716-116">Requirements</span></span>  
 <span data-ttu-id="5a716-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a716-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a716-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="5a716-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a716-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a716-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a716-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a716-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a716-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a716-121">See Also</span></span>  
    
 [<span data-ttu-id="5a716-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5a716-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5a716-123">Debug</span><span class="sxs-lookup"><span data-stu-id="5a716-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
