---
title: Metodo ICLRDebugging::CanUnloadNow
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging.CanUnloadNow Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b013231666ca6dfde5ab16e58023da1ae2a72941
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="19059-102">Metodo ICLRDebugging::CanUnloadNow</span><span class="sxs-lookup"><span data-stu-id="19059-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="19059-103">Determina se una libreria che ha fornita un [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaccia è ancora in uso o può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="19059-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19059-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19059-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19059-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="19059-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="19059-106">[in] L'indirizzo di base di un modulo nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="19059-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19059-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="19059-107">Return Value</span></span>  
 <span data-ttu-id="19059-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="19059-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="19059-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19059-109">HRESULT</span></span>|<span data-ttu-id="19059-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19059-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19059-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="19059-111">S_OK</span></span>|<span data-ttu-id="19059-112">Il modulo a cui fa riferimento `hmodule` può essere scaricato.</span><span class="sxs-lookup"><span data-stu-id="19059-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="19059-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="19059-113">S_FALSE</span></span>|<span data-ttu-id="19059-114">Il modulo a cui fa riferimento `hmodule` è ancora in uso.</span><span class="sxs-lookup"><span data-stu-id="19059-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="19059-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="19059-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="19059-116">Il modulo indicato non è un modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="19059-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="19059-117">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="19059-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19059-118">Note</span><span class="sxs-lookup"><span data-stu-id="19059-118">Remarks</span></span>  
 <span data-ttu-id="19059-119">Questo metodo controlla se tutte le istanze di `ICorDebug*` interfacce sono state rilasciate e nessun thread è attualmente all'interno di una chiamata al [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="19059-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19059-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19059-120">Requirements</span></span>  
 <span data-ttu-id="19059-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19059-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19059-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="19059-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19059-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19059-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19059-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19059-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19059-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19059-125">See Also</span></span>  
 [<span data-ttu-id="19059-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="19059-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="19059-127">Debug</span><span class="sxs-lookup"><span data-stu-id="19059-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
