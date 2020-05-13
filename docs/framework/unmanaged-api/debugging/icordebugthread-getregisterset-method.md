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
ms.openlocfilehash: 606453424d34dcb22716c308d210fb257d1c37a7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378872"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="d4c9e-102">Metodo ICorDebugThread::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="d4c9e-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="d4c9e-103">Ottiene un puntatore a interfaccia al set di registri associato alla parte attiva di questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d4c9e-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4c9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4c9e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4c9e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4c9e-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="d4c9e-106">out Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugRegisterSet](icordebugregisterset-interface.md) che rappresenta il set di registri per la parte attiva di questo thread.</span><span class="sxs-lookup"><span data-stu-id="d4c9e-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4c9e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4c9e-107">Requirements</span></span>  
 <span data-ttu-id="d4c9e-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4c9e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4c9e-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4c9e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4c9e-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4c9e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4c9e-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c9e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
