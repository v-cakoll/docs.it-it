---
title: Metodo IMetaDataEmit::DefinePermissionSet
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: a0fd3fdb6dde9fd6b88ea6c64ed907c8a3e9e46d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175798"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="2f9bf-102">Metodo IMetaDataEmit::DefinePermissionSet</span><span class="sxs-lookup"><span data-stu-id="2f9bf-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="2f9bf-103">Crea una definizione per un set di autorizzazioni con la firma dei metadati specificata e ottiene un token per tale definizione del set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2f9bf-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f9bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f9bf-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f9bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f9bf-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2f9bf-106">[in] Oggetto da decorare.</span><span class="sxs-lookup"><span data-stu-id="2f9bf-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="2f9bf-107">[in] Valore [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) che specifica il tipo di sicurezza dichiarativa da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2f9bf-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="2f9bf-108">[in] BLOB di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="2f9bf-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="2f9bf-109">[in] Dimensione, in byte, `pvPermission`di .</span><span class="sxs-lookup"><span data-stu-id="2f9bf-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="2f9bf-110">[fuori] Token di autorizzazione restituito.</span><span class="sxs-lookup"><span data-stu-id="2f9bf-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f9bf-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f9bf-111">Requirements</span></span>  
 <span data-ttu-id="2f9bf-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f9bf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f9bf-113">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f9bf-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f9bf-114">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f9bf-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f9bf-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f9bf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f9bf-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f9bf-116">See also</span></span>

- [<span data-ttu-id="2f9bf-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2f9bf-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2f9bf-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2f9bf-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
