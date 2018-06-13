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
ms.openlocfilehash: f67bd427c83385b2433b9f2e97f0b54e3b29a76f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401063"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="02020-102">Metodo ICorDebugClass::GetToken</span><span class="sxs-lookup"><span data-stu-id="02020-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="02020-103">Ottiene il `TypeDef` token di metadati che fa riferimento alla definizione di questa classe.</span><span class="sxs-lookup"><span data-stu-id="02020-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02020-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02020-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02020-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="02020-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="02020-106">[out] Un puntatore a un `mdTypeDef` token che fa riferimento la definizione di questa classe.</span><span class="sxs-lookup"><span data-stu-id="02020-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02020-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02020-107">Requirements</span></span>  
 <span data-ttu-id="02020-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02020-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02020-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="02020-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02020-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="02020-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02020-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02020-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02020-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02020-112">See Also</span></span>  
 [<span data-ttu-id="02020-113">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="02020-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
