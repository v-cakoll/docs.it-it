---
title: Metodo ICorDebugModule::GetProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8770a4978ba0410d6df825320446f4ea4817e04a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="a61c8-102">Metodo ICorDebugModule::GetProcess</span><span class="sxs-lookup"><span data-stu-id="a61c8-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="a61c8-103">Ottiene il processo contenente questo modulo.</span><span class="sxs-lookup"><span data-stu-id="a61c8-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a61c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a61c8-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a61c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a61c8-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="a61c8-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo contenente questo modulo.</span><span class="sxs-lookup"><span data-stu-id="a61c8-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a61c8-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a61c8-107">Requirements</span></span>  
 <span data-ttu-id="a61c8-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a61c8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a61c8-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a61c8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a61c8-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a61c8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a61c8-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a61c8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
