---
title: Metodo IMetaDataImport::GetModuleRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e948644e4f2d91b2f1e3e3627f7adbe204dee9d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155415"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="d9922-102">Metodo IMetaDataImport::GetModuleRefProps</span><span class="sxs-lookup"><span data-stu-id="d9922-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="d9922-103">Ottiene il nome del modulo a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="d9922-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9922-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9922-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9922-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9922-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="d9922-106">[in] Il token di metadati ModuleRef che fa riferimento al modulo per ottenere informazioni sui metadati.</span><span class="sxs-lookup"><span data-stu-id="d9922-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="d9922-107">[out] Un buffer contenente il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="d9922-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d9922-108">[in] La dimensione richiesta del `szName` in caratteri "wide".</span><span class="sxs-lookup"><span data-stu-id="d9922-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d9922-109">[out] Le dimensioni restituite del `szName` in caratteri "wide".</span><span class="sxs-lookup"><span data-stu-id="d9922-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9922-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9922-110">Requirements</span></span>  
 <span data-ttu-id="d9922-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9922-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9922-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d9922-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9922-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d9922-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9922-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9922-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9922-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9922-115">See also</span></span>

- [<span data-ttu-id="d9922-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d9922-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d9922-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d9922-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
