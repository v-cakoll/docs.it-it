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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987844"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="649ab-102">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="649ab-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="649ab-103">Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="649ab-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="649ab-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="649ab-104">Methods</span></span>  
  
|<span data-ttu-id="649ab-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="649ab-105">Method</span></span>|<span data-ttu-id="649ab-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="649ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="649ab-107">Metodo IsChild</span><span class="sxs-lookup"><span data-stu-id="649ab-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="649ab-108">Determina se il frame corrente è una cornice figlio.</span><span class="sxs-lookup"><span data-stu-id="649ab-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="649ab-109">Metodo IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="649ab-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="649ab-110">Determina se l'intervallo specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="649ab-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="649ab-111">Metodo GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="649ab-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="649ab-112">Restituisce la dimensione complessiva di parametri nello stack di su sistemi operativi x86.</span><span class="sxs-lookup"><span data-stu-id="649ab-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="649ab-113">Note</span><span class="sxs-lookup"><span data-stu-id="649ab-113">Remarks</span></span>  
 <span data-ttu-id="649ab-114">Questa interfaccia estende logicamente l'interfaccia "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="649ab-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="649ab-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="649ab-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="649ab-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="649ab-116">Requirements</span></span>  
 <span data-ttu-id="649ab-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="649ab-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="649ab-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="649ab-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="649ab-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="649ab-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="649ab-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="649ab-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="649ab-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="649ab-121">See also</span></span>

- [<span data-ttu-id="649ab-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="649ab-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="649ab-123">Debug</span><span class="sxs-lookup"><span data-stu-id="649ab-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
