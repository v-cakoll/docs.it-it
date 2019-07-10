---
title: Metodo ICorDebugType::GetBase
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c24d6e9c42a091eafbe6d4bdee2bb4e055fd8852
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772042"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="94d17-102">Metodo ICorDebugType::GetBase</span><span class="sxs-lookup"><span data-stu-id="94d17-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="94d17-103">Ottiene un puntatore a interfaccia ICorDebugType che rappresenta il tipo di base, se presente, del tipo rappresentato da questo `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="94d17-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94d17-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94d17-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94d17-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="94d17-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="94d17-106">[out] Un puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta il tipo di base.</span><span class="sxs-lookup"><span data-stu-id="94d17-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94d17-107">Note</span><span class="sxs-lookup"><span data-stu-id="94d17-107">Remarks</span></span>  
 <span data-ttu-id="94d17-108">Cercare il tipo di base per un tipo è utile per implementare le funzionalità comuni del debugger, ad esempio stampando tutti i campi di un oggetto o delle relative classi padre.</span><span class="sxs-lookup"><span data-stu-id="94d17-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94d17-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94d17-109">Requirements</span></span>  
 <span data-ttu-id="94d17-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94d17-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94d17-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94d17-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94d17-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94d17-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94d17-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94d17-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
