---
title: Metodo IMetaDataImport::GetScopeProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 53e77a7bf0bd0aafc205469c4e101f8bfdcbe80b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="f6097-102">Metodo IMetaDataImport::GetScopeProps</span><span class="sxs-lookup"><span data-stu-id="f6097-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="f6097-103">Ottiene il nome ed eventualmente l'identificatore di versione dell'assembly o del modulo nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="f6097-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6097-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6097-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6097-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6097-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="f6097-106">[out] Un buffer per il nome di assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="f6097-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f6097-107">[in] La dimensione in caratteri "wide" di `szName`.</span><span class="sxs-lookup"><span data-stu-id="f6097-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f6097-108">[out] Il numero di caratteri "wide" restituiti in `szName`.</span><span class="sxs-lookup"><span data-stu-id="f6097-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="f6097-109">[out, facoltativo] Un puntatore a un GUID che identifica in modo univoco la versione dell'assembly o modulo.</span><span class="sxs-lookup"><span data-stu-id="f6097-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6097-110">Note</span><span class="sxs-lookup"><span data-stu-id="f6097-110">Remarks</span></span>  
 <span data-ttu-id="f6097-111">Il [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) metodo viene utilizzato per impostare queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="f6097-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6097-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6097-112">Requirements</span></span>  
 <span data-ttu-id="f6097-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6097-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6097-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f6097-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6097-115">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6097-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6097-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6097-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6097-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6097-117">See Also</span></span>  
 [<span data-ttu-id="f6097-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f6097-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f6097-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f6097-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
