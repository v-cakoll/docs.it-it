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
ms.openlocfilehash: f2f19987d22502acbe06bd5e5c14b0d6c17cbe24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781575"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="62430-102">Metodo ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="62430-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="62430-103">Notifica al debugger che una classe viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="62430-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62430-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62430-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62430-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="62430-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="62430-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente la classe.</span><span class="sxs-lookup"><span data-stu-id="62430-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="62430-107">in Puntatore a un oggetto ICorDebugClass che rappresenta la classe.</span><span class="sxs-lookup"><span data-stu-id="62430-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62430-108">Note</span><span class="sxs-lookup"><span data-stu-id="62430-108">Remarks</span></span>  
 <span data-ttu-id="62430-109">Non è necessario fare riferimento alla classe dopo questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="62430-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62430-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="62430-110">Requirements</span></span>  
 <span data-ttu-id="62430-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62430-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62430-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62430-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62430-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62430-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62430-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62430-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62430-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62430-115">See also</span></span>

- [<span data-ttu-id="62430-116">Metodo LoadClass</span><span class="sxs-lookup"><span data-stu-id="62430-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="62430-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="62430-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
