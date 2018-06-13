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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d752eb17b956e2367e8b191080a370506a61ff34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416667"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="f3983-102">Metodo ICorDebugProcess::GetID</span><span class="sxs-lookup"><span data-stu-id="f3983-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="f3983-103">Ottiene l'ID del sistema operativo () del processo.</span><span class="sxs-lookup"><span data-stu-id="f3983-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3983-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3983-104">Syntax</span></span>  
  
```  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3983-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3983-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="f3983-106">[out] ID univoco del processo.</span><span class="sxs-lookup"><span data-stu-id="f3983-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3983-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3983-107">Requirements</span></span>  
 <span data-ttu-id="f3983-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3983-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3983-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f3983-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3983-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f3983-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3983-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3983-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
