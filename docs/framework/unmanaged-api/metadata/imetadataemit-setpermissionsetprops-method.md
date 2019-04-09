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
ms.openlocfilehash: 510c33b8e0e26bead00dcb85a6ceba102a5f267d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163774"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="53426-102">Metodo IMetaDataEmit::SetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="53426-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="53426-103">Imposta o aggiorna le funzionalità della firma dei metadati di un set di autorizzazioni definito da una chiamata precedente a [DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="53426-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53426-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53426-104">Syntax</span></span>  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53426-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="53426-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="53426-106">[in] Un token di metadati che rappresenta l'oggetto per essere decorata.</span><span class="sxs-lookup"><span data-stu-id="53426-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="53426-107">[in] Oggetto [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valore che specifica il tipo di sicurezza dichiarativa da usare.</span><span class="sxs-lookup"><span data-stu-id="53426-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="53426-108">[in] L'autorizzazione di BLOB.</span><span class="sxs-lookup"><span data-stu-id="53426-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="53426-109">[in] Le dimensioni, in byte, di `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="53426-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="53426-110">[out] Un `mdPermission` token di metadati che rappresenta le autorizzazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="53426-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53426-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53426-111">Requirements</span></span>  
 <span data-ttu-id="53426-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53426-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53426-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="53426-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53426-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="53426-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="53426-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="53426-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="53426-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53426-116">See also</span></span>

- [<span data-ttu-id="53426-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="53426-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="53426-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="53426-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
