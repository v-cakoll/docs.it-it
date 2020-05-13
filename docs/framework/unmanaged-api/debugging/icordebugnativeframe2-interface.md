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
ms.openlocfilehash: cd2a2821128ad9265e8a831f7b02792e6453b1ee
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213790"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="c9ed2-102">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="c9ed2-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="c9ed2-103">Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="c9ed2-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9ed2-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c9ed2-104">Methods</span></span>  
  
|<span data-ttu-id="c9ed2-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c9ed2-105">Method</span></span>|<span data-ttu-id="c9ed2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9ed2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9ed2-107">Metodo IsChild</span><span class="sxs-lookup"><span data-stu-id="c9ed2-107">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="c9ed2-108">Determina se il frame corrente è un frame figlio.</span><span class="sxs-lookup"><span data-stu-id="c9ed2-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="c9ed2-109">Metodo IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="c9ed2-109">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="c9ed2-110">Determina se il frame specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="c9ed2-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="c9ed2-111">Metodo GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="c9ed2-111">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="c9ed2-112">Restituisce la dimensione cumulativa dei parametri nello stack nei sistemi operativi x86.</span><span class="sxs-lookup"><span data-stu-id="c9ed2-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9ed2-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c9ed2-113">Remarks</span></span>  
 <span data-ttu-id="c9ed2-114">Questa interfaccia estende logicamente l'interfaccia "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="c9ed2-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9ed2-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="c9ed2-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9ed2-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9ed2-116">Requirements</span></span>  
 <span data-ttu-id="c9ed2-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9ed2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9ed2-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9ed2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9ed2-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9ed2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9ed2-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9ed2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9ed2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9ed2-121">See also</span></span>

- [<span data-ttu-id="c9ed2-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c9ed2-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c9ed2-123">Debug</span><span class="sxs-lookup"><span data-stu-id="c9ed2-123">Debugging</span></span>](index.md)
