---
title: Metodo ICorDebugManagedCallback::UnloadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3eb8bf59ee2a91c62a6ff74b1903d92607a9ffe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197873"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="da2b9-102">Metodo ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="da2b9-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="da2b9-103">Notifica al debugger che è in corso lo scaricamento di una classe.</span><span class="sxs-lookup"><span data-stu-id="da2b9-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da2b9-104">Syntax</span></span>  
  
```  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da2b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da2b9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="da2b9-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente la classe.</span><span class="sxs-lookup"><span data-stu-id="da2b9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="da2b9-107">[in] Un puntatore a un oggetto ICorDebugClass che rappresenta la classe.</span><span class="sxs-lookup"><span data-stu-id="da2b9-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da2b9-108">Note</span><span class="sxs-lookup"><span data-stu-id="da2b9-108">Remarks</span></span>  
 <span data-ttu-id="da2b9-109">La classe non dovrebbe essere specificata dopo questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="da2b9-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da2b9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da2b9-110">Requirements</span></span>  
 <span data-ttu-id="da2b9-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da2b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da2b9-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da2b9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da2b9-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da2b9-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="da2b9-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="da2b9-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da2b9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da2b9-115">See also</span></span>

- [<span data-ttu-id="da2b9-116">Metodo LoadClass</span><span class="sxs-lookup"><span data-stu-id="da2b9-116">LoadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="da2b9-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="da2b9-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
