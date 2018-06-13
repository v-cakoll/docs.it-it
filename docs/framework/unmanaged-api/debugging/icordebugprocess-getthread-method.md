---
title: Metodo ICorDebugProcess::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 008f945b5301894261ce1529cbd915dd614b919d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418955"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="41783-102">Metodo ICorDebugProcess::GetThread</span><span class="sxs-lookup"><span data-stu-id="41783-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="41783-103">Ottiene il thread del processo con l'ID del thread di sistema operativo specificato (sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="41783-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41783-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41783-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41783-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="41783-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="41783-106">[in] ID del thread da recuperare thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="41783-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="41783-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="41783-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41783-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41783-108">Requirements</span></span>  
 <span data-ttu-id="41783-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41783-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41783-110">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="41783-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41783-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="41783-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41783-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41783-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
