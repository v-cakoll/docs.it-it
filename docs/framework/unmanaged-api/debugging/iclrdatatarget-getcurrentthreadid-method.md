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
ms.openlocfilehash: 35515d7c2b82ec2c42461406363964e0b60eb243
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785461"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="16e6b-102">Metodo ICLRDataTarget::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="16e6b-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="16e6b-103">Ottiene l'identificatore del sistema operativo per il thread corrente.</span><span class="sxs-lookup"><span data-stu-id="16e6b-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16e6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16e6b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16e6b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16e6b-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="16e6b-106">out Puntatore all'identificatore del sistema operativo del thread corrente per il processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="16e6b-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16e6b-107">Note</span><span class="sxs-lookup"><span data-stu-id="16e6b-107">Remarks</span></span>  
 <span data-ttu-id="16e6b-108">Se non è presente alcun thread corrente per il processo di destinazione, il `GetCurrentThreadID` metodo potrebbe non riuscire.</span><span class="sxs-lookup"><span data-stu-id="16e6b-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16e6b-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="16e6b-109">Requirements</span></span>  
 <span data-ttu-id="16e6b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16e6b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16e6b-111">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="16e6b-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="16e6b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16e6b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16e6b-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16e6b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e6b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16e6b-114">See also</span></span>

- [<span data-ttu-id="16e6b-115">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="16e6b-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
