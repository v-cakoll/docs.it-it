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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992316"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="72f86-102">Metodo IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="72f86-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="72f86-103">Enumera le autorizzazioni per gli oggetti in un ambito dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="72f86-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72f86-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="72f86-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="72f86-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="72f86-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="72f86-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="72f86-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="72f86-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="72f86-108">[in] Token di metadati che limita l'ambito della ricerca, o NULL per la ricerca nell'ambito più ampio possibile.</span><span class="sxs-lookup"><span data-stu-id="72f86-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="72f86-109">[in] Flag che rappresenta il <xref:System.Security.Permissions.SecurityAction> valori da includere in `rPermission`, oppure zero per restituire tutte le azioni.</span><span class="sxs-lookup"><span data-stu-id="72f86-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="72f86-110">[out] Matrice utilizzata per archiviare i token di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="72f86-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="72f86-111">[in] Dimensione massima della matrice `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="72f86-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="72f86-112">[out] Il numero di token di autorizzazione restituiti in `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="72f86-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72f86-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="72f86-113">Return Value</span></span>  
  
|<span data-ttu-id="72f86-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72f86-114">HRESULT</span></span>|<span data-ttu-id="72f86-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72f86-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="72f86-116">`EnumPermissionSets` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="72f86-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="72f86-117">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="72f86-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="72f86-118">In tal caso, `pcTokens` è uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="72f86-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="72f86-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72f86-119">Requirements</span></span>  
 <span data-ttu-id="72f86-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72f86-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72f86-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="72f86-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72f86-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="72f86-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72f86-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72f86-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f86-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72f86-124">See also</span></span>

- [<span data-ttu-id="72f86-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="72f86-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="72f86-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="72f86-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
