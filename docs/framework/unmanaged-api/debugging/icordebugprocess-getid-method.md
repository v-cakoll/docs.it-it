---
title: Metodo ICorDebugProcess::GetID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
ms.openlocfilehash: 8cd40ffb60bf837a9aa3b0db34892350a05964d7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213283"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="0bab1-102">Metodo ICorDebugProcess::GetID</span><span class="sxs-lookup"><span data-stu-id="0bab1-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="0bab1-103">Ottiene l'ID del sistema operativo (OS) del processo.</span><span class="sxs-lookup"><span data-stu-id="0bab1-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bab1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0bab1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bab1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0bab1-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="0bab1-106">out ID univoco del processo.</span><span class="sxs-lookup"><span data-stu-id="0bab1-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bab1-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0bab1-107">Requirements</span></span>  
 <span data-ttu-id="0bab1-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bab1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bab1-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bab1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bab1-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bab1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bab1-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bab1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
