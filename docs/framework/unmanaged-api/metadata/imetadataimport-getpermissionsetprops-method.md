---
title: Metodo IMetaDataImport::GetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 806f1ebcacb9e7ad27b7370f9976b3341bf64f8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466934"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="10094-102">Metodo IMetaDataImport::GetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="10094-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="10094-103">Ottiene i metadati associati il <xref:System.Security.PermissionSet?displayProperty=nameWithType> rappresentato dal token Permission specificato.</span><span class="sxs-lookup"><span data-stu-id="10094-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10094-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10094-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10094-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="10094-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="10094-106">[in] Il token di metadati di autorizzazione che rappresenta l'autorizzazione impostata per ottenere le proprietà dei metadati.</span><span class="sxs-lookup"><span data-stu-id="10094-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="10094-107">[out] Puntatore al set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="10094-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="10094-108">[out] Un puntatore per la firma binaria dei metadati del set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="10094-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="10094-109">[out] La dimensione in byte di `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="10094-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10094-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10094-110">Requirements</span></span>  
 <span data-ttu-id="10094-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10094-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10094-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="10094-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10094-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="10094-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10094-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10094-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10094-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10094-115">See also</span></span>
- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="10094-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="10094-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="10094-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="10094-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
