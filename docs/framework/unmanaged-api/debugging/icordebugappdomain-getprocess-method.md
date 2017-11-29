---
title: Metodo ICorDebugAppDomain::GetProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetProcess method [.NET Framework debugging]
ms.assetid: 9d0b9628-a91c-40d0-b9bc-00b34a396b8f
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 27c092c029f259ed64eda26401bb9085f23d2bfa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetprocess-method"></a><span data-ttu-id="40ba1-102">Metodo ICorDebugAppDomain::GetProcess</span><span class="sxs-lookup"><span data-stu-id="40ba1-102">ICorDebugAppDomain::GetProcess Method</span></span>
<span data-ttu-id="40ba1-103">Ottiene il processo che contiene il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="40ba1-103">Gets the process containing the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40ba1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40ba1-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40ba1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="40ba1-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="40ba1-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo.</span><span class="sxs-lookup"><span data-stu-id="40ba1-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40ba1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40ba1-107">Requirements</span></span>  
 <span data-ttu-id="40ba1-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40ba1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40ba1-109">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="40ba1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40ba1-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40ba1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40ba1-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40ba1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
