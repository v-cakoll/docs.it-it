---
title: Metodo ICorDebugModule2::GetJITCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
ms.openlocfilehash: 1216629fc7e1c3e720d5f296b9293b3c4b7f8721
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127900"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="2b059-102">Metodo ICorDebugModule2::GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="2b059-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="2b059-103">Ottiene i flag che controllano la compilazione JIT (just-in-Time) di questo ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="2b059-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b059-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b059-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b059-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b059-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="2b059-106">out Puntatore a un valore dell'enumerazione [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) che controlla la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="2b059-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b059-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b059-107">Requirements</span></span>  
 <span data-ttu-id="2b059-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b059-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b059-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b059-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b059-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b059-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b059-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b059-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
