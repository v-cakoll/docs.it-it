---
title: Metodo IMetaDataImport::GetTypeRefProps
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25482ee81d5210e5ab69007767aecf01435602d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448596"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="c8847-102">Metodo IMetaDataImport::GetTypeRefProps</span><span class="sxs-lookup"><span data-stu-id="c8847-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="c8847-103">Ottiene i metadati associati di <xref:System.Type> a cui fa riferimento il token TypeRef specificato.</span><span class="sxs-lookup"><span data-stu-id="c8847-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8847-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8847-104">Syntax</span></span>  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8847-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8847-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="c8847-106">[in] Il token TypeRef che rappresenta il tipo da restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="c8847-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="c8847-107">[out] Un puntatore all'ambito in cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="c8847-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="c8847-108">Questo valore è un token AssemblyRef o ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="c8847-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="c8847-109">[out] Un buffer contenente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="c8847-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c8847-110">[in] La dimensione in caratteri wide della richiesta `szName`.</span><span class="sxs-lookup"><span data-stu-id="c8847-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="c8847-111">[out] Dimensione restituita in caratteri "wide" di `szName`.</span><span class="sxs-lookup"><span data-stu-id="c8847-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8847-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8847-112">Requirements</span></span>  
 <span data-ttu-id="c8847-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8847-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8847-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c8847-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8847-115">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c8847-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c8847-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8847-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8847-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8847-117">See Also</span></span>  
 [<span data-ttu-id="c8847-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c8847-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c8847-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c8847-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
