---
title: Metodo ICorDebugThread2::GetVolatileOSThreadID
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetVolatileOSThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetVolatileOSThreadID
helpviewer_keywords:
- GetVolatileOSThreadID method [.NET Framework debugging]
- ICorDebugThread2::GetVolatileOSThreadID method [.NET Framework debugging]
ms.assetid: f0922545-c2cf-40c8-9ef6-ca033563e682
topic_type:
- apiref
ms.openlocfilehash: e8d59d617efa7656a3034d5c5e009a46b6121cdb
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377652"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="cda58-102">Metodo ICorDebugThread2::GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="cda58-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>
<span data-ttu-id="cda58-103">Ottiene l'identificatore del thread del sistema operativo per questo ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="cda58-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda58-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cda58-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cda58-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cda58-105">Parameters</span></span>  
 `pdwTid`  
 <span data-ttu-id="cda58-106">out Identificatore del thread del sistema operativo per questo thread.</span><span class="sxs-lookup"><span data-stu-id="cda58-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cda58-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cda58-107">Requirements</span></span>  
 <span data-ttu-id="cda58-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cda58-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cda58-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cda58-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cda58-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cda58-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cda58-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cda58-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
