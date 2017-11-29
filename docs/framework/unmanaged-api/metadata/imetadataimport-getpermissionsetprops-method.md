---
title: Metodo IMetaDataImport::GetPermissionSetProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPermissionSetProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2556c0beee7a21d2f01c403ab141054e5bf68177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="03650-102">Metodo IMetaDataImport::GetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="03650-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="03650-103">Ottiene i metadati associati con la <xref:System.Security.PermissionSet?displayProperty=nameWithType> rappresentato dal token di autorizzazione specificato.</span><span class="sxs-lookup"><span data-stu-id="03650-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03650-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="03650-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03650-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="03650-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="03650-106">[in] Il token di metadati di autorizzazione che rappresenta l'autorizzazione impostata per ottenere le proprietà dei metadati.</span><span class="sxs-lookup"><span data-stu-id="03650-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="03650-107">[out] Puntatore al set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="03650-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="03650-108">[out] Un puntatore per la firma binaria dei metadati del set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="03650-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="03650-109">[out] Le dimensioni in byte di `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="03650-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03650-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="03650-110">Requirements</span></span>  
 <span data-ttu-id="03650-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03650-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03650-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="03650-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03650-113">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03650-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03650-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03650-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03650-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03650-115">See Also</span></span>  
 <xref:System.Security.PermissionSet>  
 [<span data-ttu-id="03650-116">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="03650-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="03650-117">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="03650-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
