---
title: Metodo ICorDebugProcess::GetThread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da5acebb9cb90efa69b0f553a1480e5e6883d079
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="f1edd-102">Metodo ICorDebugProcess::GetThread</span><span class="sxs-lookup"><span data-stu-id="f1edd-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="f1edd-103">Ottiene il thread del processo con l'ID del thread di sistema operativo specificato (sistema operativo).</span><span class="sxs-lookup"><span data-stu-id="f1edd-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1edd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1edd-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1edd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1edd-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="f1edd-106">[in] ID del thread da recuperare thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f1edd-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="f1edd-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread.</span><span class="sxs-lookup"><span data-stu-id="f1edd-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1edd-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1edd-108">Requirements</span></span>  
 <span data-ttu-id="f1edd-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1edd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1edd-110">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f1edd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1edd-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1edd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1edd-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1edd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
