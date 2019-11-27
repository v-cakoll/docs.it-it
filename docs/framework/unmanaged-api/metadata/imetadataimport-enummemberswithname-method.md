---
title: Metodo IMetaDataImport::EnumMembersWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
ms.openlocfilehash: ed193aab8beb0de1321aa1d52ec9f963b08b316c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441658"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="56921-102">Metodo IMetaDataImport::EnumMembersWithName</span><span class="sxs-lookup"><span data-stu-id="56921-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="56921-103">Enumera i token MemberDef che rappresentano i membri del tipo specificato con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="56921-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56921-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56921-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56921-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56921-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="56921-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="56921-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="56921-107">in Token TypeDef che rappresenta il tipo con i membri da enumerare.</span><span class="sxs-lookup"><span data-stu-id="56921-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="56921-108">in Nome del membro che limita l'ambito dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="56921-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="56921-109">out Matrice utilizzata per archiviare i token MemberDef.</span><span class="sxs-lookup"><span data-stu-id="56921-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="56921-110">[in] Dimensione massima della matrice `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="56921-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="56921-111">out Numero effettivo di token MemberDef restituiti in `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="56921-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56921-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="56921-112">Remarks</span></span>  
 <span data-ttu-id="56921-113">Questo metodo enumera i campi e i metodi, ma non le proprietà o gli eventi.</span><span class="sxs-lookup"><span data-stu-id="56921-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="56921-114">A differenza di [IMetaDataImport:: EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` Elimina tutti i token dei campi e dei membri che non hanno il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="56921-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56921-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="56921-115">Return Value</span></span>  
  
|<span data-ttu-id="56921-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56921-116">HRESULT</span></span>|<span data-ttu-id="56921-117">description</span><span class="sxs-lookup"><span data-stu-id="56921-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="56921-118">`EnumTypeDefs` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="56921-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="56921-119">Nessun token MemberDef da enumerare.</span><span class="sxs-lookup"><span data-stu-id="56921-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="56921-120">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="56921-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56921-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56921-121">Requirements</span></span>  
 <span data-ttu-id="56921-122">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56921-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56921-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="56921-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56921-124">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="56921-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="56921-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56921-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56921-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56921-126">See also</span></span>

- [<span data-ttu-id="56921-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="56921-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="56921-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="56921-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
