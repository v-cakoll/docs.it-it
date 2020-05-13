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
ms.openlocfilehash: a7b71170f58ddfe0295da28b8c9fc73286b074e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212269"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a><span data-ttu-id="6fad3-102">Metodo ICorDebugManagedCallback::UnloadClass</span><span class="sxs-lookup"><span data-stu-id="6fad3-102">ICorDebugManagedCallback::UnloadClass Method</span></span>
<span data-ttu-id="6fad3-103">Notifica al debugger che una classe viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="6fad3-103">Notifies the debugger that a class is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fad3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fad3-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fad3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6fad3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6fad3-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente la classe.</span><span class="sxs-lookup"><span data-stu-id="6fad3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the class.</span></span>  
  
 `c`  
 <span data-ttu-id="6fad3-107">in Puntatore a un oggetto ICorDebugClass che rappresenta la classe.</span><span class="sxs-lookup"><span data-stu-id="6fad3-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fad3-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6fad3-108">Remarks</span></span>  
 <span data-ttu-id="6fad3-109">Non è necessario fare riferimento alla classe dopo questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="6fad3-109">The class should not be referenced after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fad3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6fad3-110">Requirements</span></span>  
 <span data-ttu-id="6fad3-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fad3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fad3-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fad3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fad3-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fad3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fad3-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fad3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fad3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fad3-115">See also</span></span>

- [<span data-ttu-id="6fad3-116">Metodo LoadClass</span><span class="sxs-lookup"><span data-stu-id="6fad3-116">LoadClass Method</span></span>](icordebugmanagedcallback-loadclass-method.md)
- [<span data-ttu-id="6fad3-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="6fad3-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
