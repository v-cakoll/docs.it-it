---
title: Metodo IMetaDataImport::FindMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e59cc440ba004545c31d6b25d36cca4fdfb58899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="20e7f-102">Metodo IMetaDataImport::FindMethod</span><span class="sxs-lookup"><span data-stu-id="20e7f-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="20e7f-103">Ottiene un puntatore al MethodDef token per il metodo che è racchiuso da specificato <xref:System.Type> e con la firma di nome e i metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="20e7f-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20e7f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20e7f-104">Syntax</span></span>  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20e7f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="20e7f-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="20e7f-106">[in] Il `mdTypeDef` token per il tipo (una classe o interfaccia) che include il membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="20e7f-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="20e7f-107">Se questo valore è `mdTokenNil`, quindi viene eseguita la ricerca per una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="20e7f-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="20e7f-108">[in] Il nome del metodo da cercare.</span><span class="sxs-lookup"><span data-stu-id="20e7f-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="20e7f-109">[in] Un puntatore per la firma binaria dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="20e7f-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="20e7f-110">[in] Le dimensioni in byte di `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="20e7f-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="20e7f-111">[out] Puntatore al token MethodDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="20e7f-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20e7f-112">Note</span><span class="sxs-lookup"><span data-stu-id="20e7f-112">Remarks</span></span>  
 <span data-ttu-id="20e7f-113">Specificare il metodo utilizzando la classe o interfaccia di inclusione (`td`), il nome (`szName`) e facoltativamente la firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="20e7f-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="20e7f-114">Potrebbero essere presenti più metodi con lo stesso nome in una classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="20e7f-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="20e7f-115">In tal caso, passare la firma del metodo per trovare una corrispondenza univoca.</span><span class="sxs-lookup"><span data-stu-id="20e7f-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="20e7f-116">La firma passata a `FindMethod` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito.</span><span class="sxs-lookup"><span data-stu-id="20e7f-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="20e7f-117">Una firma è possibile incorporare un token che identifica il tipo di classe o un valore che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="20e7f-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="20e7f-118">Il token è un indice nella tabella TypeDef locale.</span><span class="sxs-lookup"><span data-stu-id="20e7f-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="20e7f-119">Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input a `FindMethod`.</span><span class="sxs-lookup"><span data-stu-id="20e7f-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="20e7f-120">`FindMethod`Trova solo i metodi che sono stati definiti direttamente nella classe o interfaccia. metodi ereditati non viene trovato.</span><span class="sxs-lookup"><span data-stu-id="20e7f-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20e7f-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20e7f-121">Requirements</span></span>  
 <span data-ttu-id="20e7f-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20e7f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20e7f-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="20e7f-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20e7f-124">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20e7f-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20e7f-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20e7f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e7f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20e7f-126">See Also</span></span>  
 <xref:System.Reflection.MethodInfo>  
 [<span data-ttu-id="20e7f-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="20e7f-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="20e7f-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="20e7f-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
