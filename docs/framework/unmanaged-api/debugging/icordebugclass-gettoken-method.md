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
ms.openlocfilehash: 6964c931307a40f384ad8a8e355cab0aad575ec6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125767"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="3123e-102">Metodo ICorDebugClass::GetToken</span><span class="sxs-lookup"><span data-stu-id="3123e-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="3123e-103">Ottiene il token di metadati `TypeDef` che fa riferimento alla definizione di questa classe.</span><span class="sxs-lookup"><span data-stu-id="3123e-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3123e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3123e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3123e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3123e-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="3123e-106">out Puntatore a un token di `mdTypeDef` che fa riferimento alla definizione di questa classe.</span><span class="sxs-lookup"><span data-stu-id="3123e-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3123e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3123e-107">Requirements</span></span>  
 <span data-ttu-id="3123e-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3123e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3123e-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3123e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3123e-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3123e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3123e-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3123e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3123e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3123e-112">See also</span></span>

- [<span data-ttu-id="3123e-113">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="3123e-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
