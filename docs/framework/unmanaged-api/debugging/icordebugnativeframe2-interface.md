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
ms.openlocfilehash: 22a3f39bc1f9b4e6cad1db4fd0a6480b7c04e8fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792746"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="a2f69-102">Interfaccia ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="a2f69-102">ICorDebugNativeFrame2 Interface</span></span>
<span data-ttu-id="a2f69-103">Fornisce metodi che verificano la presenza di relazioni fra frame padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="a2f69-103">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2f69-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a2f69-104">Methods</span></span>  
  
|<span data-ttu-id="a2f69-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a2f69-105">Method</span></span>|<span data-ttu-id="a2f69-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2f69-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2f69-107">Metodo IsChild</span><span class="sxs-lookup"><span data-stu-id="a2f69-107">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="a2f69-108">Determina se il frame corrente è un frame figlio.</span><span class="sxs-lookup"><span data-stu-id="a2f69-108">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="a2f69-109">Metodo IsMatchingParentFrame</span><span class="sxs-lookup"><span data-stu-id="a2f69-109">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="a2f69-110">Determina se il frame specificato è l'elemento padre del frame corrente.</span><span class="sxs-lookup"><span data-stu-id="a2f69-110">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="a2f69-111">Metodo GetStackParameterSize</span><span class="sxs-lookup"><span data-stu-id="a2f69-111">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="a2f69-112">Restituisce la dimensione cumulativa dei parametri nello stack nei sistemi operativi x86.</span><span class="sxs-lookup"><span data-stu-id="a2f69-112">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2f69-113">Note</span><span class="sxs-lookup"><span data-stu-id="a2f69-113">Remarks</span></span>  
 <span data-ttu-id="a2f69-114">Questa interfaccia estende logicamente l'interfaccia "ICorDebugNativeFrame".</span><span class="sxs-lookup"><span data-stu-id="a2f69-114">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2f69-115">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="a2f69-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2f69-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a2f69-116">Requirements</span></span>  
 <span data-ttu-id="a2f69-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2f69-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2f69-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2f69-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2f69-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2f69-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2f69-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2f69-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f69-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2f69-121">See also</span></span>

- [<span data-ttu-id="a2f69-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a2f69-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a2f69-123">Debug</span><span class="sxs-lookup"><span data-stu-id="a2f69-123">Debugging</span></span>](index.md)
