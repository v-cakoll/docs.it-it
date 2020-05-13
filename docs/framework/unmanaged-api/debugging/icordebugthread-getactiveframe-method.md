---
title: Metodo ICorDebugThread::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: 843c6df1ef41fdd3227b92275182432ad4cc43b1
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379732"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="d71f1-102">Metodo ICorDebugThread::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="d71f1-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="d71f1-103">Ottiene un puntatore a interfaccia per il frame attivo (più recente) in questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d71f1-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d71f1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d71f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d71f1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d71f1-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="d71f1-106">out Puntatore all'indirizzo di un oggetto interfaccia ICorDebugFrame che rappresenta un frame.</span><span class="sxs-lookup"><span data-stu-id="d71f1-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d71f1-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d71f1-107">Remarks</span></span>  
 <span data-ttu-id="d71f1-108">Il `ppFrame` parametro è null se nessun frame è attualmente attivo.</span><span class="sxs-lookup"><span data-stu-id="d71f1-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d71f1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d71f1-109">Requirements</span></span>  
 <span data-ttu-id="d71f1-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d71f1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d71f1-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d71f1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d71f1-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d71f1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d71f1-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d71f1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
