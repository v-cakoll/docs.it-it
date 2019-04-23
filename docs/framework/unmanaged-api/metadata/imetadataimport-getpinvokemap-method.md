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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121706"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="85ef2-102">Metodo IMetaDataImport::GetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="85ef2-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="85ef2-103">Ottiene un token ModuleRef per rappresentare l'assembly di destinazione di una chiamata PInvoke.</span><span class="sxs-lookup"><span data-stu-id="85ef2-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85ef2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85ef2-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="85ef2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="85ef2-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="85ef2-106">[in] Un token FieldDef o MethodDef per ottenere i metadati di mapping PInvoke per.</span><span class="sxs-lookup"><span data-stu-id="85ef2-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="85ef2-107">[out] Puntatore al flag utilizzati per il mapping.</span><span class="sxs-lookup"><span data-stu-id="85ef2-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="85ef2-108">Questo valore è una maschera di bit di [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="85ef2-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="85ef2-109">[out] Nome della DLL di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="85ef2-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="85ef2-110">[in] La dimensione in caratteri "wide" di `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="85ef2-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="85ef2-111">[out] Il numero di caratteri "wide", restituito nel `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="85ef2-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="85ef2-112">[out] Puntatore a un token ModuleRef che rappresenta la libreria di oggetti di destinazione non gestita.</span><span class="sxs-lookup"><span data-stu-id="85ef2-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85ef2-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85ef2-113">Requirements</span></span>  
 <span data-ttu-id="85ef2-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85ef2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85ef2-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="85ef2-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85ef2-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="85ef2-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85ef2-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85ef2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ef2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85ef2-118">See also</span></span>

- [<span data-ttu-id="85ef2-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="85ef2-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="85ef2-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="85ef2-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
