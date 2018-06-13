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
ms.openlocfilehash: 3d1e0f0d57440f0074a7ca179955a7a13e41f5d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415854"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="120d8-102">Metodo ICorDebugModule::GetToken</span><span class="sxs-lookup"><span data-stu-id="120d8-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="120d8-103">Ottiene il token per la voce della tabella per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="120d8-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="120d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="120d8-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="120d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="120d8-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="120d8-106">[out] Un puntatore al `mdModule` token che fa riferimento ai metadati del modulo.</span><span class="sxs-lookup"><span data-stu-id="120d8-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="120d8-107">Note</span><span class="sxs-lookup"><span data-stu-id="120d8-107">Remarks</span></span>  
 <span data-ttu-id="120d8-108">Il token può essere passato al [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), e [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfacce di importazione di metadati.</span><span class="sxs-lookup"><span data-stu-id="120d8-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="120d8-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="120d8-109">Requirements</span></span>  
 <span data-ttu-id="120d8-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="120d8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="120d8-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="120d8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="120d8-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="120d8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="120d8-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="120d8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120d8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="120d8-114">See Also</span></span>  
 [<span data-ttu-id="120d8-115">Metadati</span><span class="sxs-lookup"><span data-stu-id="120d8-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
