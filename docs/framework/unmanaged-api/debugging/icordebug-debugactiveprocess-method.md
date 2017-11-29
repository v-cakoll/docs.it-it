---
title: Metodo ICorDebug::DebugActiveProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.DebugActiveProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c17345caaec71e4d4b057bdcfc2cc395014cbf82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="7d03a-102">Metodo ICorDebug::DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="7d03a-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="7d03a-103">Collega il debugger a un processo esistente.</span><span class="sxs-lookup"><span data-stu-id="7d03a-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d03a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d03a-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d03a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7d03a-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="7d03a-106">[in] L'ID del processo a cui il debugger deve essere collegato.</span><span class="sxs-lookup"><span data-stu-id="7d03a-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="7d03a-107">[in] Valore booleano che è impostato su `true` se il debugger deve comportarsi come il debugger di Win32 per il processo e inviare i callback non gestiti; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7d03a-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="7d03a-108">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugProcess" che rappresenta il processo a cui è stato connesso il debugger.</span><span class="sxs-lookup"><span data-stu-id="7d03a-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d03a-109">Note</span><span class="sxs-lookup"><span data-stu-id="7d03a-109">Remarks</span></span>  
 <span data-ttu-id="7d03a-110">Debug di interoperabilità non è supportato sulle piattaforme Win9x e non x86, ad esempio piattaforme basate su IA-64 e AMD64 basato su.</span><span class="sxs-lookup"><span data-stu-id="7d03a-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d03a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d03a-111">Requirements</span></span>  
 <span data-ttu-id="7d03a-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d03a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d03a-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7d03a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d03a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d03a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d03a-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d03a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d03a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d03a-116">See Also</span></span>  
 [<span data-ttu-id="7d03a-117">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="7d03a-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
