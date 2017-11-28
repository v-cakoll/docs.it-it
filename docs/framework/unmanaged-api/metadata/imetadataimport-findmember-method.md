---
title: Metodo IMetaDataImport::FindMember
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMember
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a47060575d14e1206e715ea2bfd2ea750bd49c91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="fe896-102">Metodo IMetaDataImport::FindMember</span><span class="sxs-lookup"><span data-stu-id="fe896-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="fe896-103">Ottiene un puntatore al MemberDef token di campo o metodo incluso dall'oggetto <xref:System.Type> e con la firma di nome e i metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="fe896-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe896-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe896-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe896-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe896-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="fe896-106">[in] Il token TypeDef per la classe o interfaccia che include il membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="fe896-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="fe896-107">Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una variabile globale o una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="fe896-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="fe896-108">[in] Il nome del membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="fe896-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="fe896-109">[in] Un puntatore per la firma binaria dei metadati del membro.</span><span class="sxs-lookup"><span data-stu-id="fe896-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="fe896-110">[in] Le dimensioni in byte di `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="fe896-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="fe896-111">[out] Puntatore al token MemberDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="fe896-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe896-112">Note</span><span class="sxs-lookup"><span data-stu-id="fe896-112">Remarks</span></span>  
 <span data-ttu-id="fe896-113">Specificare il membro utilizzando la classe o interfaccia di inclusione (`td`), il nome (`szName`) e facoltativamente la firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="fe896-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="fe896-114">Potrebbero essere presenti più membri con lo stesso nome in una classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="fe896-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="fe896-115">In tal caso, passare la firma del membro per trovare una corrispondenza univoca.</span><span class="sxs-lookup"><span data-stu-id="fe896-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="fe896-116">La firma passata a `FindMember` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito.</span><span class="sxs-lookup"><span data-stu-id="fe896-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="fe896-117">Una firma è possibile incorporare un token che identifica il tipo di classe o un valore che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="fe896-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="fe896-118">Il token è un indice nella tabella TypeDef locale.</span><span class="sxs-lookup"><span data-stu-id="fe896-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="fe896-119">Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input a `FindMember`.</span><span class="sxs-lookup"><span data-stu-id="fe896-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="fe896-120">`FindMember`Trova solo i membri che sono stati definiti direttamente nella classe o interfaccia. i membri ereditati non viene trovato.</span><span class="sxs-lookup"><span data-stu-id="fe896-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe896-121">`FindMember`è un metodo di supporto.</span><span class="sxs-lookup"><span data-stu-id="fe896-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="fe896-122">Chiama [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); se la chiamata non trova una corrispondenza, `FindMember` chiama quindi [FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="fe896-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe896-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe896-123">Requirements</span></span>  
 <span data-ttu-id="fe896-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe896-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe896-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fe896-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe896-126">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe896-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe896-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe896-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe896-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe896-128">See Also</span></span>  
 [<span data-ttu-id="fe896-129">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fe896-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="fe896-130">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="fe896-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
