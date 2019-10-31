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
ms.openlocfilehash: a81842132769934a6f5f34e6dc462bba77b3854a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138682"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="fe50b-102">Metodo ICorDebugThread2::GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="fe50b-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="fe50b-103">Ottiene l'identificatore di connessione per questo oggetto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="fe50b-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe50b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe50b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe50b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe50b-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="fe50b-106">out `CONNID` che rappresenta l'identificatore di connessione.</span><span class="sxs-lookup"><span data-stu-id="fe50b-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe50b-107">Note</span><span class="sxs-lookup"><span data-stu-id="fe50b-107">Remarks</span></span>  
 <span data-ttu-id="fe50b-108">Il metodo `GetConnectionID` restituisce zero nel parametro `pdwConnectionId`, se il thread non fa parte di una connessione.</span><span class="sxs-lookup"><span data-stu-id="fe50b-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="fe50b-109">Se il thread è connesso a un'istanza di Microsoft SQL Server 2005 Analysis Services (SSAS), il `CONNID` viene mappato a un identificatore di processo del server (SPID).</span><span class="sxs-lookup"><span data-stu-id="fe50b-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe50b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe50b-110">Requirements</span></span>  
 <span data-ttu-id="fe50b-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe50b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe50b-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe50b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe50b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe50b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe50b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe50b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
