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
ms.openlocfilehash: 3433f5f69927afb501c2596571f138e3a69fabb6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894118"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="f334f-102">Metodo ICorDebugClass::GetToken</span><span class="sxs-lookup"><span data-stu-id="f334f-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="f334f-103">Ottiene il `TypeDef` token di metadati che fa riferimento alla definizione di questa classe.</span><span class="sxs-lookup"><span data-stu-id="f334f-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f334f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f334f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f334f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f334f-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="f334f-106">out Puntatore a un `mdTypeDef` token che fa riferimento alla definizione di questa classe.</span><span class="sxs-lookup"><span data-stu-id="f334f-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f334f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f334f-107">Requirements</span></span>  
 <span data-ttu-id="f334f-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f334f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f334f-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f334f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f334f-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f334f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f334f-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f334f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f334f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f334f-112">See also</span></span>

- [<span data-ttu-id="f334f-113">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="f334f-113">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
