---
title: Metodo ICLRDataTarget::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
ms.openlocfilehash: ccb5cda11a2466496a4b3981e8185cbb7130f66f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122901"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="f83e7-102">Metodo ICLRDataTarget::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="f83e7-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="f83e7-103">Ottiene l'identificatore del sistema operativo per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="f83e7-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f83e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f83e7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f83e7-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="f83e7-106">out Puntatore all'identificatore del sistema operativo del thread corrente per il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f83e7-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f83e7-107">Note</span><span class="sxs-lookup"><span data-stu-id="f83e7-107">Remarks</span></span>  
 <span data-ttu-id="f83e7-108">Se non è presente alcun thread corrente per il processo di destinazione, il `GetCurrentThreadID` metodo potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="f83e7-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f83e7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f83e7-109">Requirements</span></span>  
 <span data-ttu-id="f83e7-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f83e7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f83e7-111">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="f83e7-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f83e7-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f83e7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f83e7-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f83e7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83e7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f83e7-114">See also</span></span>

- [<span data-ttu-id="f83e7-115">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="f83e7-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
