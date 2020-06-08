---
title: Metodo IMetaDataImport::FindMember
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: fce4f3875fbdb110134d6b7f684eff40821f6bdd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503679"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="63c56-102">Metodo IMetaDataImport::FindMember</span><span class="sxs-lookup"><span data-stu-id="63c56-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="63c56-103">Ottiene un puntatore al token MemberDef per il campo o il metodo racchiuso dall'oggetto specificato <xref:System.Type> e con il nome e la firma dei metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="63c56-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63c56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63c56-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63c56-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63c56-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="63c56-106">in Token TypeDef per la classe o l'interfaccia che racchiude il membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="63c56-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="63c56-107">Se questo valore è `mdTokenNil` , la ricerca viene eseguita per una variabile globale o una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="63c56-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="63c56-108">in Nome del membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="63c56-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="63c56-109">in Puntatore alla firma dei metadati binari del membro.</span><span class="sxs-lookup"><span data-stu-id="63c56-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="63c56-110">in Dimensioni in byte di `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="63c56-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="63c56-111">out Puntatore al token MemberDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="63c56-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63c56-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="63c56-112">Remarks</span></span>  
 <span data-ttu-id="63c56-113">È possibile specificare il membro utilizzando la classe o l'interfaccia di inclusione ( `td` ), il nome ( `szName` ) e facoltativamente la relativa firma () `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="63c56-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="63c56-114">Potrebbero essere presenti più membri con lo stesso nome in una classe o in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="63c56-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="63c56-115">In tal caso, passare la firma del membro per trovare la corrispondenza univoca.</span><span class="sxs-lookup"><span data-stu-id="63c56-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="63c56-116">La firma passata a `FindMember` deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico.</span><span class="sxs-lookup"><span data-stu-id="63c56-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="63c56-117">Una firma può incorporare un token che identifica la classe o il tipo di valore contenitore.</span><span class="sxs-lookup"><span data-stu-id="63c56-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="63c56-118">Il token è un indice nella tabella TypeDef locale.</span><span class="sxs-lookup"><span data-stu-id="63c56-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="63c56-119">Non è possibile compilare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per l'input `FindMember` .</span><span class="sxs-lookup"><span data-stu-id="63c56-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="63c56-120">`FindMember`trova solo i membri definiti direttamente nella classe o nell'interfaccia. non vengono trovati membri ereditati.</span><span class="sxs-lookup"><span data-stu-id="63c56-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63c56-121">`FindMember`è un metodo helper.</span><span class="sxs-lookup"><span data-stu-id="63c56-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="63c56-122">Chiama [IMetaDataImport:: FindMethod](imetadataimport-findmethod-method.md); Se la chiamata non trova una corrispondenza, `FindMember` chiama [IMetaDataImport:: FindField](imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="63c56-122">It calls [IMetaDataImport::FindMethod](imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63c56-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63c56-123">Requirements</span></span>  
 <span data-ttu-id="63c56-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63c56-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63c56-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="63c56-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63c56-126">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="63c56-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="63c56-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63c56-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c56-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63c56-128">See also</span></span>

- [<span data-ttu-id="63c56-129">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="63c56-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="63c56-130">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="63c56-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
