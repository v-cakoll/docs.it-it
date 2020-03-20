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
ms.openlocfilehash: e628cf5dab8006b0df0ab6c60dc995cd0c6bb29d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175447"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="0a06a-102">Metodo IMetaDataImport::EnumPermissionSets</span><span class="sxs-lookup"><span data-stu-id="0a06a-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="0a06a-103">Enumera le autorizzazioni per gli oggetti in un ambito dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="0a06a-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a06a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a06a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a06a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a06a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0a06a-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="0a06a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0a06a-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="0a06a-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="0a06a-108">[in] Token di metadati che limita l'ambito della ricerca oppure NULL per eseguire la ricerca nell'ambito più ampio possibile.</span><span class="sxs-lookup"><span data-stu-id="0a06a-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="0a06a-109">[in] Flag che <xref:System.Security.Permissions.SecurityAction> rappresentano i `rPermission`valori da includere in , o zero per restituire tutte le azioni.</span><span class="sxs-lookup"><span data-stu-id="0a06a-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="0a06a-110">[fuori] Matrice utilizzata per archiviare i token di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="0a06a-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0a06a-111">[in] Dimensione massima della matrice `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="0a06a-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0a06a-112">[fuori] Numero di token di autorizzazione `rPermission`restituiti in .</span><span class="sxs-lookup"><span data-stu-id="0a06a-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a06a-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0a06a-113">Return Value</span></span>  
  
|<span data-ttu-id="0a06a-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a06a-114">HRESULT</span></span>|<span data-ttu-id="0a06a-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a06a-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0a06a-116">`EnumPermissionSets`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="0a06a-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0a06a-117">Non sono presenti token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="0a06a-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="0a06a-118">In tal `pcTokens` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="0a06a-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0a06a-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a06a-119">Requirements</span></span>  
 <span data-ttu-id="0a06a-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a06a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a06a-121">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a06a-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a06a-122">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a06a-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a06a-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a06a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a06a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a06a-124">See also</span></span>

- [<span data-ttu-id="0a06a-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0a06a-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0a06a-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0a06a-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
