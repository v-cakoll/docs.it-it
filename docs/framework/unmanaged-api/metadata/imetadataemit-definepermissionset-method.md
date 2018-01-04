---
title: Metodo IMetaDataEmit::DefinePermissionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefinePermissionSet
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74bea316d3f56e007c4b75e6b801d8c82ae8ce96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="577a0-102">Metodo IMetaDataEmit::DefinePermissionSet</span><span class="sxs-lookup"><span data-stu-id="577a0-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="577a0-103">Crea una definizione per un set di autorizzazioni con la firma dei metadati specificati e ottiene un token per tale definizione di set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="577a0-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="577a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="577a0-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="577a0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="577a0-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="577a0-106">[in] Oggetto da essere decorata.</span><span class="sxs-lookup"><span data-stu-id="577a0-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="577a0-107">[in] Oggetto [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valore che specifica il tipo di sicurezza dichiarativa da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="577a0-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="577a0-108">[in] BLOB di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="577a0-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="577a0-109">[in] Le dimensioni, in byte, di `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="577a0-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="577a0-110">[out] Token di autorizzazione restituito.</span><span class="sxs-lookup"><span data-stu-id="577a0-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="577a0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="577a0-111">Requirements</span></span>  
 <span data-ttu-id="577a0-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="577a0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="577a0-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="577a0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="577a0-114">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="577a0-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="577a0-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="577a0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="577a0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="577a0-116">See Also</span></span>  
 [<span data-ttu-id="577a0-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="577a0-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="577a0-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="577a0-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
