---
title: Metodo ICorDebugModule::GetAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
ms.openlocfilehash: 29c9d9dde4776ef729c0bbae7b644171a265e3ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137458"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="a13f7-102">Metodo ICorDebugModule::GetAssembly</span><span class="sxs-lookup"><span data-stu-id="a13f7-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="a13f7-103">Ottiene l'assembly contenitore per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="a13f7-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a13f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a13f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a13f7-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="a13f7-106">out Puntatore a un oggetto ICorDebugAssembly che rappresenta l'assembly contenente il modulo.</span><span class="sxs-lookup"><span data-stu-id="a13f7-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13f7-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a13f7-107">Requirements</span></span>  
 <span data-ttu-id="a13f7-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a13f7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a13f7-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a13f7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a13f7-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a13f7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a13f7-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a13f7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
