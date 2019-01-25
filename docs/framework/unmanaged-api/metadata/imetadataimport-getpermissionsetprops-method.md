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
ms.openlocfilehash: bdee4df6964097f1c333a8fe96756a8898f7c1cc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598932"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="c2b32-102">Metodo IMetaDataImport::GetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="c2b32-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="c2b32-103">Ottiene i metadati associati il <xref:System.Security.PermissionSet?displayProperty=nameWithType> rappresentato dal token Permission specificato.</span><span class="sxs-lookup"><span data-stu-id="c2b32-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2b32-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2b32-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c2b32-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="c2b32-106">[in] Il token di metadati di autorizzazione che rappresenta l'autorizzazione impostata per ottenere le proprietà dei metadati.</span><span class="sxs-lookup"><span data-stu-id="c2b32-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="c2b32-107">[out] Puntatore al set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c2b32-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="c2b32-108">[out] Un puntatore per la firma binaria dei metadati del set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c2b32-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="c2b32-109">[out] La dimensione in byte di `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="c2b32-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2b32-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2b32-110">Requirements</span></span>  
 <span data-ttu-id="c2b32-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2b32-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b32-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c2b32-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2b32-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c2b32-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2b32-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2b32-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b32-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2b32-115">See also</span></span>
- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="c2b32-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c2b32-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c2b32-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c2b32-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
