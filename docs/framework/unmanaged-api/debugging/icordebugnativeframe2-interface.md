---
title: Interfaccia ICorDebugNativeFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc664d308d4db3e97597d785eda159e32255fa54
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520373"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="ce6a0-102">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="ce6a0-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="ce6a0-103">Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce6a0-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ce6a0-104">Methods</span></span>  
  
|<span data-ttu-id="ce6a0-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ce6a0-105">Method</span></span>|<span data-ttu-id="ce6a0-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce6a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce6a0-107">Metodo IsChild</span><span class="sxs-lookup"><span data-stu-id="ce6a0-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="ce6a0-108">Determina se il frame corrente è una cornice figlio.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="ce6a0-109">Metodo IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="ce6a0-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="ce6a0-110">Determina se l'intervallo specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="ce6a0-111">Metodo GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="ce6a0-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="ce6a0-112">Restituisce la dimensione complessiva di parametri nello stack di su sistemi operativi x86.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce6a0-113">Note</span><span class="sxs-lookup"><span data-stu-id="ce6a0-113">Remarks</span></span>  
 <span data-ttu-id="ce6a0-114">Questa interfaccia estende logicamente l'interfaccia "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="ce6a0-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce6a0-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="ce6a0-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce6a0-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce6a0-116">Requirements</span></span>  
 <span data-ttu-id="ce6a0-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce6a0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce6a0-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce6a0-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce6a0-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce6a0-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce6a0-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce6a0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce6a0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce6a0-121">See also</span></span>

- [<span data-ttu-id="ce6a0-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ce6a0-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ce6a0-123">Debug</span><span class="sxs-lookup"><span data-stu-id="ce6a0-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
