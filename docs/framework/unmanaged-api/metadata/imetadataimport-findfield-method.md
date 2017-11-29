---
title: Metodo IMetaDataImport::FindField
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2178f8738ca510fb2163c1043dd94ebcb7043904
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="22807-102">Metodo IMetaDataImport::FindField</span><span class="sxs-lookup"><span data-stu-id="22807-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="22807-103">Ottiene un puntatore al FieldDef token per il campo che è racchiuso da specificato <xref:System.Type> e con la firma di nome e i metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="22807-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22807-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22807-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22807-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22807-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="22807-106">[in] Il token TypeDef per la classe o interfaccia che racchiude il campo per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="22807-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="22807-107">Se questo valore è `mdTokenNil`, la ricerca verrà eseguita per una variabile globale.</span><span class="sxs-lookup"><span data-stu-id="22807-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="22807-108">[in] Il nome del campo per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="22807-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="22807-109">[in] Un puntatore per la firma binaria dei metadati del campo.</span><span class="sxs-lookup"><span data-stu-id="22807-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="22807-110">[in] Le dimensioni in byte di `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="22807-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="22807-111">[out] Puntatore al token FieldDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="22807-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22807-112">Note</span><span class="sxs-lookup"><span data-stu-id="22807-112">Remarks</span></span>  
 <span data-ttu-id="22807-113">Specificare il campo utilizzando la classe o interfaccia di inclusione (`td`), il nome (`szName`) e facoltativamente la firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="22807-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="22807-114">La firma passata a `FindField` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito.</span><span class="sxs-lookup"><span data-stu-id="22807-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="22807-115">Una firma è possibile incorporare un token che identifica il tipo di classe o un valore che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="22807-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="22807-116">Il token è un indice nella tabella TypeDef locale.</span><span class="sxs-lookup"><span data-stu-id="22807-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="22807-117">Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per `FindField`.</span><span class="sxs-lookup"><span data-stu-id="22807-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="22807-118">`FindField`Trova solo i campi che sono stati definiti direttamente nella classe o interfaccia. i campi ereditati non viene trovato.</span><span class="sxs-lookup"><span data-stu-id="22807-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22807-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22807-119">Requirements</span></span>  
 <span data-ttu-id="22807-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22807-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22807-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="22807-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22807-122">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22807-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22807-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22807-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22807-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22807-124">See Also</span></span>  
 [<span data-ttu-id="22807-125">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="22807-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="22807-126">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="22807-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
