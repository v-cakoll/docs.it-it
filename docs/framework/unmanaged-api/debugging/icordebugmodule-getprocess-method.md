---
title: Metodo ICorDebugModule::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
ms.openlocfilehash: c10c45c4450e02d633ebeeca15da95b7c95ff0b4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212529"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="181f3-102">Metodo ICorDebugModule::GetProcess</span><span class="sxs-lookup"><span data-stu-id="181f3-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="181f3-103">Ottiene il processo contenitore del modulo.</span><span class="sxs-lookup"><span data-stu-id="181f3-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="181f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="181f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="181f3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="181f3-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="181f3-106">out Puntatore all'indirizzo di un oggetto ICorDebugProcess che rappresenta il processo che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="181f3-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="181f3-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="181f3-107">Requirements</span></span>  
 <span data-ttu-id="181f3-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="181f3-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="181f3-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="181f3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="181f3-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="181f3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="181f3-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="181f3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
