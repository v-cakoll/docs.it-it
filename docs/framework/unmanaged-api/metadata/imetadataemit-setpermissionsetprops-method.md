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
ms.openlocfilehash: de4cfdf2a9353eebdebaf4df9e481d06d776ff04
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177494"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="a1e6f-102">Metodo IMetaDataEmit::SetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="a1e6f-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="a1e6f-103">Imposta o aggiorna le funzionalità della firma dei metadati di un set di autorizzazioni definito da una precedente chiamata a [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1e6f-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1e6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1e6f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1e6f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1e6f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="a1e6f-106">[in] Token di metadati che rappresenta l'oggetto da decorare.</span><span class="sxs-lookup"><span data-stu-id="a1e6f-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="a1e6f-107">[in] Valore [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) che specifica il tipo di sicurezza dichiarativa da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a1e6f-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="a1e6f-108">[in] BLOB di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a1e6f-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="a1e6f-109">[in] Dimensione, in byte, `pvPermission`di .</span><span class="sxs-lookup"><span data-stu-id="a1e6f-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="a1e6f-110">[fuori] Token `mdPermission` di metadati che rappresenta le autorizzazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="a1e6f-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1e6f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1e6f-111">Requirements</span></span>  
 <span data-ttu-id="a1e6f-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1e6f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1e6f-113">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a1e6f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1e6f-114">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1e6f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1e6f-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1e6f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e6f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1e6f-116">See also</span></span>

- [<span data-ttu-id="a1e6f-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a1e6f-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a1e6f-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a1e6f-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
