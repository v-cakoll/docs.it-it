---
title: Metodo IMetaDataImport::EnumMethodImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: e766cec8fd84713e12c43cd1095650ed5b757bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175473"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="93e1d-102">Metodo IMetaDataImport::EnumMethodImpls</span><span class="sxs-lookup"><span data-stu-id="93e1d-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="93e1d-103">Enumera i token MethodBody e MethodDeclaration che rappresentano i metodi del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="93e1d-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93e1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93e1d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93e1d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="93e1d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="93e1d-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="93e1d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="93e1d-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="93e1d-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="93e1d-108">[in] Token TypeDef per il tipo di cui il metodo viene inizializzato per l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="93e1d-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="93e1d-109">[fuori] Matrice in cui archiviare i token MethodBody.</span><span class="sxs-lookup"><span data-stu-id="93e1d-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="93e1d-110">[fuori] Matrice in cui archiviare i token MethodDeclaration.</span><span class="sxs-lookup"><span data-stu-id="93e1d-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="93e1d-111">[in] Dimensione massima delle `rMethodBody` `rMethodDecl` matrici e .</span><span class="sxs-lookup"><span data-stu-id="93e1d-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="93e1d-112">[in] Numero effettivo di metodi `rMethodBody` restituiti in e `rMethodDecl`.</span><span class="sxs-lookup"><span data-stu-id="93e1d-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93e1d-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="93e1d-113">Return Value</span></span>  
  
|<span data-ttu-id="93e1d-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93e1d-114">HRESULT</span></span>|<span data-ttu-id="93e1d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="93e1d-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="93e1d-116">`EnumMethodImpls`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="93e1d-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="93e1d-117">Non sono presenti token di metodo da enumerare.</span><span class="sxs-lookup"><span data-stu-id="93e1d-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="93e1d-118">In tal `pcTokens` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="93e1d-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93e1d-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93e1d-119">Requirements</span></span>  
 <span data-ttu-id="93e1d-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93e1d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93e1d-121">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="93e1d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93e1d-122">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93e1d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93e1d-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93e1d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e1d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93e1d-124">See also</span></span>

- [<span data-ttu-id="93e1d-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="93e1d-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="93e1d-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="93e1d-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
