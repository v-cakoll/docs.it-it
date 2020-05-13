---
title: Metodo ICorDebugModule::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: a6aff37a480460bfed7064d59b4c5276daf3207c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212503"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="5c12c-102">Metodo ICorDebugModule::GetToken</span><span class="sxs-lookup"><span data-stu-id="5c12c-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="5c12c-103">Ottiene il token per la voce della tabella per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="5c12c-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c12c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c12c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c12c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c12c-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="5c12c-106">out Puntatore al `mdModule` token che fa riferimento ai metadati del modulo.</span><span class="sxs-lookup"><span data-stu-id="5c12c-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c12c-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5c12c-107">Remarks</span></span>  
 <span data-ttu-id="5c12c-108">Il token può essere passato alle interfacce di importazione dei metadati [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)e [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5c12c-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c12c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c12c-109">Requirements</span></span>  
 <span data-ttu-id="5c12c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c12c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c12c-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c12c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c12c-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c12c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c12c-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c12c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c12c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c12c-114">See also</span></span>

- [<span data-ttu-id="5c12c-115">Metadati</span><span class="sxs-lookup"><span data-stu-id="5c12c-115">Metadata</span></span>](../metadata/index.md)
