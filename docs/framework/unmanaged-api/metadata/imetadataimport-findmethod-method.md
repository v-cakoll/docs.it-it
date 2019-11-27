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
ms.openlocfilehash: 470b6511366cef1680eaf97f9ab376736add55c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437891"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="c7a54-102">Metodo IMetaDataImport::FindMethod</span><span class="sxs-lookup"><span data-stu-id="c7a54-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="c7a54-103">Ottiene un puntatore al token MethodDef per il metodo racchiuso dall'<xref:System.Type> specificato e con il nome e la firma dei metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="c7a54-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7a54-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7a54-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7a54-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7a54-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c7a54-106">in Token `mdTypeDef` per il tipo (una classe o interfaccia) che racchiude il membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="c7a54-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="c7a54-107">Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="c7a54-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="c7a54-108">in Nome del metodo da cercare.</span><span class="sxs-lookup"><span data-stu-id="c7a54-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c7a54-109">in Puntatore alla firma dei metadati binari del metodo.</span><span class="sxs-lookup"><span data-stu-id="c7a54-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c7a54-110">in Dimensioni in byte del `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="c7a54-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="c7a54-111">out Puntatore al token MethodDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c7a54-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7a54-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c7a54-112">Remarks</span></span>  
 <span data-ttu-id="c7a54-113">Il metodo viene specificato utilizzando la classe o l'interfaccia di inclusione (`td`), il nome (`szName`) e, facoltativamente, la relativa firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="c7a54-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="c7a54-114">Potrebbero essere presenti più metodi con lo stesso nome in una classe o in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c7a54-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="c7a54-115">In tal caso, passare la firma del metodo per trovare la corrispondenza univoca.</span><span class="sxs-lookup"><span data-stu-id="c7a54-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="c7a54-116">La firma passata a `FindMethod` deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico.</span><span class="sxs-lookup"><span data-stu-id="c7a54-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="c7a54-117">Una firma può incorporare un token che identifica la classe o il tipo di valore contenitore.</span><span class="sxs-lookup"><span data-stu-id="c7a54-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="c7a54-118">Il token è un indice nella tabella TypeDef locale.</span><span class="sxs-lookup"><span data-stu-id="c7a54-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="c7a54-119">Non è possibile compilare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per l'input per `FindMethod`.</span><span class="sxs-lookup"><span data-stu-id="c7a54-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="c7a54-120">`FindMethod` trova solo i metodi definiti direttamente nella classe o nell'interfaccia; non trova metodi ereditati.</span><span class="sxs-lookup"><span data-stu-id="c7a54-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7a54-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7a54-121">Requirements</span></span>  
 <span data-ttu-id="c7a54-122">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7a54-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7a54-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c7a54-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c7a54-124">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c7a54-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7a54-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7a54-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a54-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7a54-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="c7a54-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c7a54-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c7a54-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c7a54-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
