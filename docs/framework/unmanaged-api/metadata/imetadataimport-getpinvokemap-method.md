---
title: Metodo IMetaDataImport::GetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99aea385cf5e3c8bcf7cf39b7cc5618f99f8a631
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121706"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="f0db9-102">Metodo IMetaDataImport::GetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="f0db9-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="f0db9-103">Ottiene un token ModuleRef per rappresentare l'assembly di destinazione di una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="f0db9-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0db9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0db9-104">Syntax</span></span>  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0db9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0db9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f0db9-106">[in] Un token FieldDef o MethodDef per ottenere i metadati di mapping PInvoke per.</span><span class="sxs-lookup"><span data-stu-id="f0db9-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="f0db9-107">[out] Puntatore al flag utilizzati per il mapping.</span><span class="sxs-lookup"><span data-stu-id="f0db9-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="f0db9-108">Questo valore è una maschera di bit di [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f0db9-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="f0db9-109">[out] Nome della DLL di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="f0db9-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="f0db9-110">[in] La dimensione in caratteri "wide" di `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="f0db9-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="f0db9-111">[out] Il numero di caratteri "wide", restituito nel `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="f0db9-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="f0db9-112">[out] Puntatore a un token ModuleRef che rappresenta la libreria di oggetti di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="f0db9-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0db9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0db9-113">Requirements</span></span>  
 <span data-ttu-id="f0db9-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0db9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0db9-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f0db9-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0db9-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f0db9-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f0db9-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f0db9-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0db9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0db9-118">See also</span></span>

- [<span data-ttu-id="f0db9-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f0db9-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f0db9-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f0db9-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
