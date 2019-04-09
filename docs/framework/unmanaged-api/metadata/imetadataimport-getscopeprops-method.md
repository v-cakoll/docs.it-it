---
title: Metodo IMetaDataImport::GetScopeProps
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 17568a46c8e946989af0e401366d7eaa885886da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220968"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="8f9d4-102">Metodo IMetaDataImport::GetScopeProps</span><span class="sxs-lookup"><span data-stu-id="8f9d4-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="8f9d4-103">Ottiene il nome ed eventualmente l'identificatore di versione dell'assembly o del modulo nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="8f9d4-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f9d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f9d4-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f9d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f9d4-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="8f9d4-106">[out] Un buffer per il nome assembly o un modulo.</span><span class="sxs-lookup"><span data-stu-id="8f9d4-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="8f9d4-107">[in] La dimensione in caratteri "wide" di `szName`.</span><span class="sxs-lookup"><span data-stu-id="8f9d4-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="8f9d4-108">[out] Il numero di caratteri "wide", restituito nel `szName`.</span><span class="sxs-lookup"><span data-stu-id="8f9d4-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="8f9d4-109">[out, optional] Puntatore a un GUID che identifica la versione dell'assembly o del modulo.</span><span class="sxs-lookup"><span data-stu-id="8f9d4-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f9d4-110">Note</span><span class="sxs-lookup"><span data-stu-id="8f9d4-110">Remarks</span></span>  
 <span data-ttu-id="8f9d4-111">Il [SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) metodo viene utilizzato per impostare queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="8f9d4-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f9d4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f9d4-112">Requirements</span></span>  
 <span data-ttu-id="8f9d4-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f9d4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f9d4-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8f9d4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f9d4-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8f9d4-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8f9d4-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8f9d4-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f9d4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f9d4-117">See also</span></span>

- [<span data-ttu-id="8f9d4-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="8f9d4-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8f9d4-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="8f9d4-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
