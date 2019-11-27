---
title: Metodo IMetaDataImport::FindField
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
ms.openlocfilehash: 842d6c0deb90bc45cb59454fb30fcc3544d742f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437945"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="bc824-102">Metodo IMetaDataImport::FindField</span><span class="sxs-lookup"><span data-stu-id="bc824-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="bc824-103">Ottiene un puntatore al token FieldDef per il campo racchiuso dall'<xref:System.Type> specificato e con il nome e la firma dei metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="bc824-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc824-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bc824-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc824-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bc824-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bc824-106">in Token TypeDef per la classe o l'interfaccia che racchiude il campo da ricercare.</span><span class="sxs-lookup"><span data-stu-id="bc824-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="bc824-107">Se questo valore è `mdTokenNil`, la ricerca viene eseguita per una variabile globale.</span><span class="sxs-lookup"><span data-stu-id="bc824-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="bc824-108">in Nome del campo da ricercare.</span><span class="sxs-lookup"><span data-stu-id="bc824-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="bc824-109">in Puntatore alla firma dei metadati binari del campo.</span><span class="sxs-lookup"><span data-stu-id="bc824-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="bc824-110">in Dimensioni in byte del `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="bc824-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="bc824-111">out Puntatore al token FieldDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bc824-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc824-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bc824-112">Remarks</span></span>  
 <span data-ttu-id="bc824-113">Il campo viene specificato utilizzando la classe o l'interfaccia di inclusione (`td`), il nome (`szName`) e, facoltativamente, la relativa firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="bc824-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="bc824-114">La firma passata a `FindField` deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico.</span><span class="sxs-lookup"><span data-stu-id="bc824-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="bc824-115">Una firma può incorporare un token che identifica la classe o il tipo di valore contenitore.</span><span class="sxs-lookup"><span data-stu-id="bc824-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="bc824-116">(Il token è un indice nella tabella TypeDef locale).</span><span class="sxs-lookup"><span data-stu-id="bc824-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="bc824-117">Non è possibile compilare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per `FindField`.</span><span class="sxs-lookup"><span data-stu-id="bc824-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="bc824-118">`FindField` trova solo i campi definiti direttamente nella classe o nell'interfaccia; non trova i campi ereditati.</span><span class="sxs-lookup"><span data-stu-id="bc824-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc824-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bc824-119">Requirements</span></span>  
 <span data-ttu-id="bc824-120">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc824-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc824-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bc824-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bc824-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bc824-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bc824-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc824-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc824-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc824-124">See also</span></span>

- [<span data-ttu-id="bc824-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bc824-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bc824-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bc824-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
