---
title: Metodo IMetaDataImport::GetTypeRefProps
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
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 23dbfe2468088da5e02fb7156606af5f3fa51044
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="968cd-102">Metodo IMetaDataImport::GetTypeRefProps</span><span class="sxs-lookup"><span data-stu-id="968cd-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="968cd-103">Ottiene i metadati associati di <xref:System.Type> a cui fa riferimento il token TypeRef specificato.</span><span class="sxs-lookup"><span data-stu-id="968cd-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="968cd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="968cd-104">Syntax</span></span>  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="968cd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="968cd-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="968cd-106">[in] Il token TypeRef che rappresenta il tipo da restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="968cd-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="968cd-107">[out] Un puntatore all'ambito in cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="968cd-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="968cd-108">Questo valore è un token AssemblyRef o ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="968cd-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="968cd-109">[out] Un buffer contenente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="968cd-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="968cd-110">[in] La dimensione in caratteri wide della richiesta `szName`.</span><span class="sxs-lookup"><span data-stu-id="968cd-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="968cd-111">[out] Dimensione restituita in caratteri "wide" di `szName`.</span><span class="sxs-lookup"><span data-stu-id="968cd-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="968cd-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="968cd-112">Requirements</span></span>  
 <span data-ttu-id="968cd-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="968cd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="968cd-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="968cd-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="968cd-115">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="968cd-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="968cd-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="968cd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="968cd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="968cd-117">See Also</span></span>  
 [<span data-ttu-id="968cd-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="968cd-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="968cd-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="968cd-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
