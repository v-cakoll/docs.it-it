---
title: Metodo IMetaDataImport::EnumMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 218b65b5899692774c434ae136a3976ecb97ea2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177301"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="a5154-102">Metodo IMetaDataImport::EnumMethods</span><span class="sxs-lookup"><span data-stu-id="a5154-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="a5154-103">Enumera i token MethodDef che rappresentano i metodi del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="a5154-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5154-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5154-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5154-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5154-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a5154-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="a5154-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a5154-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="a5154-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="a5154-108">[in] Token TypeDef che rappresenta il tipo con i metodi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="a5154-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="a5154-109">[fuori] Matrice in cui archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="a5154-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a5154-110">[in] Dimensione massima della matrice `rMethods` MethodDef.</span><span class="sxs-lookup"><span data-stu-id="a5154-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a5154-111">[fuori] Numero di token MethodDef restituiti in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="a5154-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5154-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a5154-112">Return Value</span></span>  
  
|<span data-ttu-id="a5154-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5154-113">HRESULT</span></span>|<span data-ttu-id="a5154-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5154-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a5154-115">`EnumMethods`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="a5154-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a5154-116">Non sono presenti token MethodDef da enumerare.</span><span class="sxs-lookup"><span data-stu-id="a5154-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="a5154-117">In tal `pcTokens` caso, è zero.</span><span class="sxs-lookup"><span data-stu-id="a5154-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5154-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5154-118">Requirements</span></span>  
 <span data-ttu-id="a5154-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5154-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5154-120">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5154-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5154-121">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5154-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5154-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5154-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5154-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5154-123">See also</span></span>

- [<span data-ttu-id="a5154-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a5154-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a5154-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a5154-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
