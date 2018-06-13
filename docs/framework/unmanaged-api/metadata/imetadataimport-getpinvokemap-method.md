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
ms.openlocfilehash: 2174537e9605ad35e4f6f878954e318c7032b080
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448348"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="0472d-102">Metodo IMetaDataImport::GetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="0472d-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="0472d-103">Ottiene un token ModuleRef per rappresentare l'assembly di destinazione di una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="0472d-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0472d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0472d-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="0472d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0472d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0472d-106">[in] Token FieldDef o MethodDef per ottenere i metadati di mapping per PInvoke.</span><span class="sxs-lookup"><span data-stu-id="0472d-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="0472d-107">[out] Puntatore a flag utilizzati per il mapping.</span><span class="sxs-lookup"><span data-stu-id="0472d-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="0472d-108">Questo valore è una maschera di bit di [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0472d-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="0472d-109">[out] Il nome della DLL di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="0472d-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="0472d-110">[in] La dimensione in caratteri "wide" di `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="0472d-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="0472d-111">[out] Il numero di caratteri "wide" restituiti in `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="0472d-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="0472d-112">[out] Puntatore a un token ModuleRef che rappresenta la libreria di oggetti di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="0472d-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0472d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0472d-113">Requirements</span></span>  
 <span data-ttu-id="0472d-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0472d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0472d-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0472d-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0472d-116">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0472d-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0472d-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0472d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0472d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0472d-118">See Also</span></span>  
 [<span data-ttu-id="0472d-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0472d-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="0472d-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0472d-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
