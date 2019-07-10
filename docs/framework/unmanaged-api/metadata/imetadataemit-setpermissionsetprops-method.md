---
title: Metodo IMetaDataEmit::SetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f77e6e9711f05262e494f2814750af8ef7cd9f64
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750897"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="e4ad1-102">Metodo IMetaDataEmit::SetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="e4ad1-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="e4ad1-103">Imposta o aggiorna le funzionalità della firma dei metadati di un set di autorizzazioni definito da una chiamata precedente a [DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="e4ad1-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4ad1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4ad1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4ad1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e4ad1-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e4ad1-106">[in] Un token di metadati che rappresenta l'oggetto per essere decorata.</span><span class="sxs-lookup"><span data-stu-id="e4ad1-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="e4ad1-107">[in] Oggetto [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valore che specifica il tipo di sicurezza dichiarativa da usare.</span><span class="sxs-lookup"><span data-stu-id="e4ad1-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="e4ad1-108">[in] L'autorizzazione di BLOB.</span><span class="sxs-lookup"><span data-stu-id="e4ad1-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="e4ad1-109">[in] Le dimensioni, in byte, di `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="e4ad1-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="e4ad1-110">[out] Un `mdPermission` token di metadati che rappresenta le autorizzazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="e4ad1-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4ad1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4ad1-111">Requirements</span></span>  
 <span data-ttu-id="e4ad1-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4ad1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4ad1-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e4ad1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4ad1-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e4ad1-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4ad1-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4ad1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ad1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4ad1-116">See also</span></span>

- [<span data-ttu-id="e4ad1-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e4ad1-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e4ad1-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e4ad1-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
