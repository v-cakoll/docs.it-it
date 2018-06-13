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
ms.openlocfilehash: b96c6ab8fb9065e1a08ad45a7f4482ef0b32788b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418884"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="558bd-102">Metodo ICorDebugType::GetBase</span><span class="sxs-lookup"><span data-stu-id="558bd-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="558bd-103">Ottiene un puntatore a interfaccia ICorDebugType che rappresenta il tipo di base, se presente, del tipo rappresentato da questo `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="558bd-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="558bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="558bd-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="558bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="558bd-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="558bd-106">[out] Un puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta il tipo di base.</span><span class="sxs-lookup"><span data-stu-id="558bd-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="558bd-107">Note</span><span class="sxs-lookup"><span data-stu-id="558bd-107">Remarks</span></span>  
 <span data-ttu-id="558bd-108">Cercare il tipo di base per un tipo è utile per implementare le funzionalità comuni del debugger, ad esempio la stampa tutti i campi di un oggetto o le relative classi padre.</span><span class="sxs-lookup"><span data-stu-id="558bd-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="558bd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="558bd-109">Requirements</span></span>  
 <span data-ttu-id="558bd-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="558bd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="558bd-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="558bd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="558bd-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="558bd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="558bd-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="558bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
