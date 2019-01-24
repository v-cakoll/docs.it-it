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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f87724bda78c1948ae7e1ddfa3d586fe5b7e14e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575736"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="71ea1-102">Metodo ICorDebugModule::GetToken</span><span class="sxs-lookup"><span data-stu-id="71ea1-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="71ea1-103">Ottiene il token per la voce della tabella per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="71ea1-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ea1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71ea1-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71ea1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71ea1-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="71ea1-106">[out] Un puntatore al `mdModule` token che fa riferimento a metadati del modulo.</span><span class="sxs-lookup"><span data-stu-id="71ea1-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71ea1-107">Note</span><span class="sxs-lookup"><span data-stu-id="71ea1-107">Remarks</span></span>  
 <span data-ttu-id="71ea1-108">Il token può essere passato per il [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), e [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfacce di importazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="71ea1-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71ea1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71ea1-109">Requirements</span></span>  
 <span data-ttu-id="71ea1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71ea1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71ea1-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71ea1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71ea1-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71ea1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71ea1-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ea1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ea1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71ea1-114">See also</span></span>
- [<span data-ttu-id="71ea1-115">Metadati</span><span class="sxs-lookup"><span data-stu-id="71ea1-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
