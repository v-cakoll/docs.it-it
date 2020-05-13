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
ms.openlocfilehash: c630daa50d465622c421381ac080eaa8d9d8d01d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379068"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="16d17-102">Metodo ICorDebugThread2::GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="16d17-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="16d17-103">Ottiene l'identificatore di connessione per questo oggetto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="16d17-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d17-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16d17-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16d17-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16d17-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="16d17-106">out Oggetto `CONNID` che rappresenta l'identificatore di connessione.</span><span class="sxs-lookup"><span data-stu-id="16d17-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16d17-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="16d17-107">Remarks</span></span>  
 <span data-ttu-id="16d17-108">Il `GetConnectionID` metodo restituisce zero nel `pdwConnectionId` parametro, se il thread non fa parte di una connessione.</span><span class="sxs-lookup"><span data-stu-id="16d17-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="16d17-109">Se il thread è connesso a un'istanza di Microsoft SQL Server 2005 Analysis Services (SSAS), `CONNID` esegue il mapping a un identificatore di processo del server (SPID).</span><span class="sxs-lookup"><span data-stu-id="16d17-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16d17-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16d17-110">Requirements</span></span>  
 <span data-ttu-id="16d17-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16d17-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16d17-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16d17-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16d17-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16d17-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16d17-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16d17-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
