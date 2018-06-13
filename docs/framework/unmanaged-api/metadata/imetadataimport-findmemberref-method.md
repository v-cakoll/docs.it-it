---
title: Metodo IMetaDataImport::FindMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3736d604b7e77028a2b99d462d88ae207df926c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448023"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="ee4a0-102">Metodo IMetaDataImport::FindMemberRef</span><span class="sxs-lookup"><span data-stu-id="ee4a0-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="ee4a0-103">Ottiene un riferimento che è un puntatore al token MemberRef per il membro racchiusi specificato <xref:System.Type> e con la firma di nome e i metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee4a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee4a0-104">Syntax</span></span>  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee4a0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee4a0-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ee4a0-106">[in] Il token TypeRef per la classe o interfaccia che include il riferimento al membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="ee4a0-107">Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una variabile globale o un riferimento alla funzione globale.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="ee4a0-108">[in] Il nome del riferimento al membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="ee4a0-109">[in] Un puntatore per la firma binaria dei metadati del riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ee4a0-110">[in] Le dimensioni in byte di `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="ee4a0-111">[out] Puntatore al token MemberRef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee4a0-112">Note</span><span class="sxs-lookup"><span data-stu-id="ee4a0-112">Remarks</span></span>  
 <span data-ttu-id="ee4a0-113">Specificare il membro utilizzando la classe o interfaccia di inclusione (`td`), il nome (`szName`) e facoltativamente la firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="ee4a0-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="ee4a0-114">La firma passata a `FindMemberRef` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="ee4a0-115">Una firma è possibile incorporare un token che identifica il tipo di classe o un valore che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="ee4a0-116">Il token è un indice nella tabella TypeDef locale.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="ee4a0-117">Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per `FindMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="ee4a0-118">`FindMemberRef` Trova solo i riferimenti di membro che sono stati definiti direttamente nella classe o interfaccia. non trova riferimenti ai membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="ee4a0-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee4a0-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee4a0-119">Requirements</span></span>  
 <span data-ttu-id="ee4a0-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee4a0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee4a0-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ee4a0-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee4a0-122">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ee4a0-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee4a0-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee4a0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee4a0-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee4a0-124">See Also</span></span>  
 [<span data-ttu-id="ee4a0-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ee4a0-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ee4a0-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ee4a0-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
