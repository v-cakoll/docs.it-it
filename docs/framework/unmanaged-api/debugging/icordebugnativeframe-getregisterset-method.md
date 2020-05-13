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
ms.openlocfilehash: e2055098c85c5a2e4619b9b0ddc8d602256bd16b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209721"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="b4b75-102">Metodo ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="b4b75-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="b4b75-103">Ottiene il set di registri per questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="b4b75-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4b75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4b75-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4b75-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b4b75-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="b4b75-106">out Puntatore all'indirizzo di un oggetto [ICorDebugRegisterSet](icordebugregisterset-interface.md) che rappresenta il set di registri per questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="b4b75-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4b75-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4b75-107">Requirements</span></span>  
 <span data-ttu-id="b4b75-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4b75-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4b75-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4b75-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4b75-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4b75-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4b75-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4b75-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b75-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4b75-112">See also</span></span>
