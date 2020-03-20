---
title: Metodo IMetaDataImport::FindMethod
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177257"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="86811-102">Metodo IMetaDataImport::FindMethod</span><span class="sxs-lookup"><span data-stu-id="86811-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="86811-103">Ottiene un puntatore al token MethodDef per il <xref:System.Type> metodo racchiuso tra il nome e la firma dei metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="86811-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86811-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86811-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86811-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86811-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="86811-106">[in] Token `mdTypeDef` per il tipo (una classe o un'interfaccia) che racchiude il membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="86811-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="86811-107">Se questo `mdTokenNil`valore è , la ricerca viene eseguita per una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="86811-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="86811-108">[in] Nome del metodo da cercare.</span><span class="sxs-lookup"><span data-stu-id="86811-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="86811-109">[in] Puntatore alla firma dei metadati binari del metodo.</span><span class="sxs-lookup"><span data-stu-id="86811-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="86811-110">[in] Dimensione in byte `pvSigBlob`di .</span><span class="sxs-lookup"><span data-stu-id="86811-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="86811-111">[fuori] Puntatore al token MethodDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="86811-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86811-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="86811-112">Remarks</span></span>  
 <span data-ttu-id="86811-113">Il metodo viene specificato utilizzando la`td`relativa classe`szName`o interfaccia di inclusione ( ), il nome ( ) e, facoltativamente, la firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="86811-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="86811-114">Potrebbero essere presenti più metodi con lo stesso nome in una classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="86811-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="86811-115">In tal caso, passare la firma del metodo per trovare la corrispondenza univoca.</span><span class="sxs-lookup"><span data-stu-id="86811-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="86811-116">La firma `FindMethod` passata deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico.</span><span class="sxs-lookup"><span data-stu-id="86811-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="86811-117">Una firma può incorporare un token che identifica la classe o il tipo di valore che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="86811-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="86811-118">Il token è un indice nella tabella TypeDef locale.</span><span class="sxs-lookup"><span data-stu-id="86811-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="86811-119">Non è possibile compilare un'firma in fase di esecuzione all'esterno `FindMethod`del contesto dell'ambito corrente e utilizzare tale firma come input per l'input in .</span><span class="sxs-lookup"><span data-stu-id="86811-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="86811-120">`FindMethod`trova solo i metodi che sono stati definiti direttamente nella classe o nell'interfaccia; non trova i metodi ereditati.</span><span class="sxs-lookup"><span data-stu-id="86811-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86811-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86811-121">Requirements</span></span>  
 <span data-ttu-id="86811-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86811-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86811-123">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86811-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86811-124">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86811-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86811-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86811-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86811-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86811-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="86811-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="86811-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="86811-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="86811-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
