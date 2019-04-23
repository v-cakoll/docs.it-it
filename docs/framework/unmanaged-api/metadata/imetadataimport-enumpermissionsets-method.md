---
title: Metodo IMetaDataImport::EnumPermissionSets
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28e6ad309af808638400fc27255acdee381b4c6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196697"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="a6b69-102">Metodo IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="a6b69-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="a6b69-103">Enumera le autorizzazioni per gli oggetti in un ambito dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="a6b69-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6b69-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6b69-104">Syntax</span></span>  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6b69-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6b69-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a6b69-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="a6b69-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a6b69-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="a6b69-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="a6b69-108">[in] Token di metadati che limita l'ambito della ricerca, o NULL per la ricerca nell'ambito più ampio possibile.</span><span class="sxs-lookup"><span data-stu-id="a6b69-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="a6b69-109">[in] Flag che rappresenta il <xref:System.Security.Permissions.SecurityAction> valori da includere in `rPermission`, oppure zero per restituire tutte le azioni.</span><span class="sxs-lookup"><span data-stu-id="a6b69-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="a6b69-110">[out] Matrice utilizzata per archiviare i token di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a6b69-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a6b69-111">[in] Dimensione massima della matrice `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="a6b69-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a6b69-112">[out] Il numero di token di autorizzazione restituiti in `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="a6b69-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6b69-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a6b69-113">Return Value</span></span>  
  
|<span data-ttu-id="a6b69-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6b69-114">HRESULT</span></span>|<span data-ttu-id="a6b69-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6b69-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a6b69-116">`EnumPermissionSets` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a6b69-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a6b69-117">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="a6b69-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="a6b69-118">In tal caso, `pcTokens` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="a6b69-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6b69-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6b69-119">Requirements</span></span>  
 <span data-ttu-id="a6b69-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6b69-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6b69-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a6b69-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6b69-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a6b69-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6b69-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6b69-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b69-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6b69-124">See also</span></span>

- [<span data-ttu-id="a6b69-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a6b69-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a6b69-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a6b69-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
