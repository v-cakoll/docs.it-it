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
ms.openlocfilehash: 808c48bb0c516c51f39a8424acf49869b1bc9208
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165230"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="7e23c-102">Metodo IMetaDataImport::GetTypeRefProps</span><span class="sxs-lookup"><span data-stu-id="7e23c-102">IMetaDataImport::GetTypeRefProps Method</span></span>
<span data-ttu-id="7e23c-103">Ottiene i metadati associati il <xref:System.Type> fa riferimento il token TypeRef specificato.</span><span class="sxs-lookup"><span data-stu-id="7e23c-103">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e23c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e23c-104">Syntax</span></span>  
  
```  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e23c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e23c-105">Parameters</span></span>  
 `tr`  
 <span data-ttu-id="7e23c-106">[in] Il token TypeRef che rappresenta il tipo da restituire i metadati.</span><span class="sxs-lookup"><span data-stu-id="7e23c-106">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="7e23c-107">[out] Un puntatore all'ambito in cui viene reso il riferimento.</span><span class="sxs-lookup"><span data-stu-id="7e23c-107">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="7e23c-108">Questo valore è un token ModuleRef o AssemblyRef.</span><span class="sxs-lookup"><span data-stu-id="7e23c-108">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="7e23c-109">[out] Un buffer contenente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="7e23c-109">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7e23c-110">[in] Le dimensioni richieste in caratteri wide di `szName`.</span><span class="sxs-lookup"><span data-stu-id="7e23c-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="7e23c-111">[out] Le dimensioni restituite in caratteri wide di `szName`.</span><span class="sxs-lookup"><span data-stu-id="7e23c-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e23c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e23c-112">Requirements</span></span>  
 <span data-ttu-id="7e23c-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e23c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e23c-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7e23c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e23c-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7e23c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7e23c-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e23c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e23c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e23c-117">See also</span></span>

- [<span data-ttu-id="7e23c-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7e23c-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7e23c-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7e23c-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
