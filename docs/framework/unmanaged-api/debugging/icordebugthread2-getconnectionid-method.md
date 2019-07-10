---
title: Metodo ICorDebugThread2::GetConnectionID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc4963dcf686fe62f473aea1af86868df03718df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768964"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="02d88-102">Metodo ICorDebugThread2::GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="02d88-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="02d88-103">Ottiene l'identificatore di connessione per l'oggetto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="02d88-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02d88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02d88-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="02d88-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="02d88-106">[out] Oggetto `CONNID` che rappresenta l'identificatore di connessione.</span><span class="sxs-lookup"><span data-stu-id="02d88-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02d88-107">Note</span><span class="sxs-lookup"><span data-stu-id="02d88-107">Remarks</span></span>  
 <span data-ttu-id="02d88-108">Il `GetConnectionID` metodo viene restituito zero nel `pdwConnectionId` parametro, se il thread non è parte di una connessione.</span><span class="sxs-lookup"><span data-stu-id="02d88-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="02d88-109">Se il thread è connesso a un'istanza di Microsoft SQL Server 2005 Analysis Services (SSAS), il `CONNID` esegue il mapping a un identificatore di processo server (SPID).</span><span class="sxs-lookup"><span data-stu-id="02d88-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02d88-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02d88-110">Requirements</span></span>  
 <span data-ttu-id="02d88-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02d88-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02d88-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02d88-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02d88-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02d88-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02d88-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02d88-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
