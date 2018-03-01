---
title: Metodo IMetaDataImport::GetPinvokeMap
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a28d628040a35d309515703563239a5f802dc4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="b9643-102">Metodo IMetaDataImport::GetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="b9643-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="b9643-103">Ottiene un token ModuleRef per rappresentare l'assembly di destinazione di una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="b9643-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9643-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9643-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="b9643-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9643-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b9643-106">[in] Token FieldDef o MethodDef per ottenere i metadati di mapping per PInvoke.</span><span class="sxs-lookup"><span data-stu-id="b9643-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="b9643-107">[out] Puntatore a flag utilizzati per il mapping.</span><span class="sxs-lookup"><span data-stu-id="b9643-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="b9643-108">Questo valore è una maschera di bit di [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b9643-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="b9643-109">[out] Il nome della DLL di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="b9643-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="b9643-110">[in] La dimensione in caratteri "wide" di `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="b9643-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="b9643-111">[out] Il numero di caratteri "wide" restituiti in `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="b9643-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="b9643-112">[out] Puntatore a un token ModuleRef che rappresenta la libreria di oggetti di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="b9643-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9643-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9643-113">Requirements</span></span>  
 <span data-ttu-id="b9643-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9643-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9643-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b9643-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9643-116">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9643-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9643-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9643-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9643-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9643-118">See Also</span></span>  
 [<span data-ttu-id="b9643-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b9643-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b9643-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b9643-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
