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
ms.openlocfilehash: dd8f1adee6bbcb3b57b87a2d6c85c01c624da9ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421230"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="0b48c-102">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="0b48c-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="0b48c-103">Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="0b48c-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b48c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0b48c-104">Methods</span></span>  
  
|<span data-ttu-id="0b48c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0b48c-105">Method</span></span>|<span data-ttu-id="0b48c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b48c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b48c-107">Metodo IsChild</span><span class="sxs-lookup"><span data-stu-id="0b48c-107">IsChild Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="0b48c-108">Determina se il frame corrente è un frame figlio.</span><span class="sxs-lookup"><span data-stu-id="0b48c-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="0b48c-109">Metodo IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="0b48c-109">IsMatchingParentFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="0b48c-110">Determina se l'intervallo specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="0b48c-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="0b48c-111">Metodo GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="0b48c-111">GetStackParameterSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="0b48c-112">Restituisce la dimensione complessiva dei parametri nello stack su sistemi operativi x86.</span><span class="sxs-lookup"><span data-stu-id="0b48c-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b48c-113">Note</span><span class="sxs-lookup"><span data-stu-id="0b48c-113">Remarks</span></span>  
 <span data-ttu-id="0b48c-114">Questa interfaccia estende logicamente l'interfaccia "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="0b48c-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b48c-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="0b48c-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b48c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b48c-116">Requirements</span></span>  
 <span data-ttu-id="0b48c-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b48c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b48c-118">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0b48c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b48c-119">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0b48c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b48c-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b48c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b48c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b48c-121">See Also</span></span>  
    
 [<span data-ttu-id="0b48c-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0b48c-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0b48c-123">Debug</span><span class="sxs-lookup"><span data-stu-id="0b48c-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
