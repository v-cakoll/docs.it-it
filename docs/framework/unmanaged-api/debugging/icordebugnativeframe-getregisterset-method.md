---
title: Metodo ICorDebugNativeFrame::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: affab7ae99dbdf85e7eadc89bfd24c42408626ac
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792812"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="c68ae-102">Metodo ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="c68ae-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="c68ae-103">Ottiene il set di registri per questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="c68ae-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c68ae-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c68ae-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c68ae-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c68ae-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="c68ae-106">out Puntatore all'indirizzo di un oggetto [ICorDebugRegisterSet](icordebugregisterset-interface.md) che rappresenta il set di registri per questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="c68ae-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c68ae-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c68ae-107">Requirements</span></span>  
 <span data-ttu-id="c68ae-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c68ae-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c68ae-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c68ae-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c68ae-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c68ae-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c68ae-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c68ae-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c68ae-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c68ae-112">See also</span></span>
