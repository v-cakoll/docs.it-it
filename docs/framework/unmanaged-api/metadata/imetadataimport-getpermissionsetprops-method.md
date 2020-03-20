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
ms.openlocfilehash: 5faf1a6ae89045b2ef17fab789ee6e5bf23eecf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175343"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="c638c-102">Metodo IMetaDataImport::GetPermissionSetProps</span><span class="sxs-lookup"><span data-stu-id="c638c-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="c638c-103">Ottiene i metadati <xref:System.Security.PermissionSet?displayProperty=nameWithType> associati ai rappresentati dal token di autorizzazione specificato.</span><span class="sxs-lookup"><span data-stu-id="c638c-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c638c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c638c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c638c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c638c-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="c638c-106">[in] Token di metadati Permission che rappresenta il set di autorizzazioni per cui ottenere le proprietà dei metadati.</span><span class="sxs-lookup"><span data-stu-id="c638c-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="c638c-107">[fuori] Puntatore al set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c638c-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="c638c-108">[fuori] Puntatore alla firma dei metadati binari del set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c638c-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="c638c-109">[fuori] Dimensione in byte `ppvPermission`di .</span><span class="sxs-lookup"><span data-stu-id="c638c-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c638c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c638c-110">Requirements</span></span>  
 <span data-ttu-id="c638c-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c638c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c638c-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c638c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c638c-113">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c638c-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c638c-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c638c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c638c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c638c-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="c638c-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c638c-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c638c-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c638c-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
