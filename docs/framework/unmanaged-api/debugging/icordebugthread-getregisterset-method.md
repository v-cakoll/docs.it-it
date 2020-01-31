---
title: Metodo ICorDebugThread::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
ms.openlocfilehash: 9793424e79ed878b04a5c51daad08b5d12d439e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791460"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="5bf2d-102">Metodo ICorDebugThread::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="5bf2d-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="5bf2d-103">Ottiene un puntatore a interfaccia al set di registri associato alla parte attiva di questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="5bf2d-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf2d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bf2d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bf2d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5bf2d-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="5bf2d-106">out Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugRegisterSet](icordebugregisterset-interface.md) che rappresenta il set di registri per la parte attiva di questo thread.</span><span class="sxs-lookup"><span data-stu-id="5bf2d-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bf2d-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5bf2d-107">Requirements</span></span>  
 <span data-ttu-id="5bf2d-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bf2d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf2d-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bf2d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bf2d-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bf2d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bf2d-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf2d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
