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
ms.openlocfilehash: 11ea6e468909ea42e38bdc7b76c60c460c98025e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503666"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="6ca2c-102">Metodo IMetaDataImport::FindField</span><span class="sxs-lookup"><span data-stu-id="6ca2c-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="6ca2c-103">Ottiene un puntatore al token FieldDef per il campo racchiuso dall'oggetto specificato <xref:System.Type> e con il nome e la firma dei metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="6ca2c-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ca2c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ca2c-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ca2c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ca2c-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6ca2c-106">in Token TypeDef per la classe o l'interfaccia che racchiude il campo da ricercare.</span><span class="sxs-lookup"><span data-stu-id="6ca2c-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="6ca2c-107">Se questo valore è `mdTokenNil` , la ricerca viene eseguita per una variabile globale.</span><span class="sxs-lookup"><span data-stu-id="6ca2c-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="6ca2c-108">in Nome del campo da ricercare.</span><span class="sxs-lookup"><span data-stu-id="6ca2c-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="6ca2c-109">in Puntatore alla firma dei metadati binari del campo.</span><span class="sxs-lookup"><span data-stu-id="6ca2c-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="6ca2c-110">in Dimensioni in byte di `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="6ca2c-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="6ca2c-111">out Puntatore al token FieldDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6ca2c-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ca2c-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6ca2c-112">Remarks</span></span>  
 <span data-ttu-id="6ca2c-113">Il campo viene specificato utilizzando la classe o l'interfaccia di inclusione ( `td` ), il nome ( `szName` ) e, facoltativamente, la relativa firma () `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="6ca2c-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="6ca2c-114">La firma passata a `FindField` deve essere stata generata nell'ambito corrente, perché le firme sono associate a un ambito specifico.</span><span class="sxs-lookup"><span data-stu-id="6ca2c-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="6ca2c-115">Una firma può incorporare un token che identifica la classe o il tipo di valore contenitore.</span><span class="sxs-lookup"><span data-stu-id="6ca2c-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="6ca2c-116">(Il token è un indice nella tabella TypeDef locale).</span><span class="sxs-lookup"><span data-stu-id="6ca2c-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="6ca2c-117">Non è possibile compilare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e utilizzare tale firma come input per `FindField` .</span><span class="sxs-lookup"><span data-stu-id="6ca2c-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="6ca2c-118">`FindField`trova solo i campi definiti direttamente nella classe o nell'interfaccia; non trova i campi ereditati.</span><span class="sxs-lookup"><span data-stu-id="6ca2c-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ca2c-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ca2c-119">Requirements</span></span>  
 <span data-ttu-id="6ca2c-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ca2c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ca2c-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6ca2c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ca2c-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6ca2c-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6ca2c-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ca2c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca2c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ca2c-124">See also</span></span>

- [<span data-ttu-id="6ca2c-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6ca2c-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6ca2c-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6ca2c-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
