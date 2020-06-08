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
ms.openlocfilehash: 068014732cee91147edaec29fa0f954a741d8b5c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491654"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="e9cf3-102">Metodo IMetaDataImport::FindMemberRef</span><span class="sxs-lookup"><span data-stu-id="e9cf3-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="e9cf3-103">Ottiene un puntatore al token MemberRef per il riferimento al membro racchiuso dall'oggetto specificato <xref:System.Type> e con il nome e la firma dei metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9cf3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9cf3-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9cf3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9cf3-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e9cf3-106">in Token TypeRef per la classe o l'interfaccia che racchiude il riferimento del membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="e9cf3-107">Se questo valore è `mdTokenNil` , la ricerca viene eseguita per una variabile globale o un riferimento a una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="e9cf3-108">in Nome del riferimento del membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e9cf3-109">in Puntatore alla firma dei metadati binari del riferimento al membro.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e9cf3-110">in Dimensioni in byte di `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="e9cf3-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="e9cf3-111">out Puntatore al token MemberRef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9cf3-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e9cf3-112">Remarks</span></span>  
 <span data-ttu-id="e9cf3-113">È possibile specificare il membro utilizzando la classe o l'interfaccia di inclusione ( `td` ), il nome ( `szName` ) e facoltativamente la relativa firma () `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="e9cf3-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="e9cf3-114">La firma passata a `FindMemberRef` deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="e9cf3-115">Una firma può incorporare un token che identifica la classe o il tipo di valore contenitore.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="e9cf3-116">Il token è un indice nella tabella TypeDef locale.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="e9cf3-117">Non è possibile compilare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per `FindMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="e9cf3-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="e9cf3-118">`FindMemberRef`trova solo i riferimenti ai membri definiti direttamente nella classe o nell'interfaccia. non trova riferimenti a membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="e9cf3-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9cf3-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9cf3-119">Requirements</span></span>  
 <span data-ttu-id="e9cf3-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9cf3-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9cf3-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9cf3-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9cf3-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e9cf3-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9cf3-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9cf3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9cf3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9cf3-124">See also</span></span>

- [<span data-ttu-id="e9cf3-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e9cf3-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e9cf3-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e9cf3-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
