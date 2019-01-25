---
title: Metodo ICLRDebugging::CanUnloadNow
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fd0a7322437cb89fe62729f86f5ce8005ed3b5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646750"
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="3f584-102">Metodo ICLRDebugging::CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="3f584-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="3f584-103">Determina se una libreria che ha fornita un' [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaccia è ancora in uso o può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="3f584-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f584-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f584-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f584-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f584-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="3f584-106">[in] L'indirizzo di base di un modulo nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3f584-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f584-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3f584-107">Return Value</span></span>  
 <span data-ttu-id="3f584-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="3f584-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3f584-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f584-109">HRESULT</span></span>|<span data-ttu-id="3f584-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f584-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f584-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f584-111">S_OK</span></span>|<span data-ttu-id="3f584-112">Il modulo che fa riferimento `hmodule` può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="3f584-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="3f584-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3f584-113">S_FALSE</span></span>|<span data-ttu-id="3f584-114">Il modulo che fa riferimento `hmodule` è ancora in uso.</span><span class="sxs-lookup"><span data-stu-id="3f584-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="3f584-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="3f584-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="3f584-116">Il modulo indicato non è un modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="3f584-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="3f584-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="3f584-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f584-118">Note</span><span class="sxs-lookup"><span data-stu-id="3f584-118">Remarks</span></span>  
 <span data-ttu-id="3f584-119">Questo metodo verifica se tutte le istanze di `ICorDebug*` interfacce sono state rilasciate e nessun thread si trova all'interno di una chiamata ai [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3f584-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f584-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f584-120">Requirements</span></span>  
 <span data-ttu-id="3f584-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f584-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f584-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f584-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f584-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f584-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f584-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f584-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f584-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f584-125">See also</span></span>
- [<span data-ttu-id="3f584-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3f584-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3f584-127">Debug</span><span class="sxs-lookup"><span data-stu-id="3f584-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
