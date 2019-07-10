---
title: Metodo ICorDebugClass::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b944112ce0b00e84da6243e2e48917e2318b0f1c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746838"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="0cf9e-102">Metodo ICorDebugClass::GetToken</span><span class="sxs-lookup"><span data-stu-id="0cf9e-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="0cf9e-103">Ottiene il `TypeDef` token di metadati che fa riferimento alla definizione di questa classe.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cf9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cf9e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cf9e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0cf9e-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="0cf9e-106">[out] Un puntatore a un `mdTypeDef` token che fa riferimento alla definizione di questa classe.</span><span class="sxs-lookup"><span data-stu-id="0cf9e-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cf9e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0cf9e-107">Requirements</span></span>  
 <span data-ttu-id="0cf9e-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cf9e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cf9e-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cf9e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cf9e-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cf9e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cf9e-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cf9e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf9e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cf9e-112">See also</span></span>

- [<span data-ttu-id="0cf9e-113">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="0cf9e-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
