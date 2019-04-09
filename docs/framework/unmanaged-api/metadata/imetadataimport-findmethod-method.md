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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28aa8313e7ba0c071187d0f1f6d78431b16fc005
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164801"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="ce155-102">Metodo IMetaDataImport::FindMethod</span><span class="sxs-lookup"><span data-stu-id="ce155-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="ce155-103">Ottiene un puntatore al MethodDef token per il metodo che è racchiuso da specificato <xref:System.Type> e avente il nome e i metadati della firma specificata.</span><span class="sxs-lookup"><span data-stu-id="ce155-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce155-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce155-104">Syntax</span></span>  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce155-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce155-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ce155-106">[in] Il `mdTypeDef` token per il tipo (una classe o interfaccia) che include il membro da cercare.</span><span class="sxs-lookup"><span data-stu-id="ce155-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="ce155-107">Se questo valore è `mdTokenNil`, quindi la ricerca viene eseguita per una funzione globale.</span><span class="sxs-lookup"><span data-stu-id="ce155-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="ce155-108">[in] Il nome del metodo da cercare.</span><span class="sxs-lookup"><span data-stu-id="ce155-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="ce155-109">[in] Un puntatore per la firma binaria dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="ce155-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ce155-110">[in] La dimensione in byte di `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="ce155-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="ce155-111">[out] Puntatore al token MethodDef corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ce155-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce155-112">Note</span><span class="sxs-lookup"><span data-stu-id="ce155-112">Remarks</span></span>  
 <span data-ttu-id="ce155-113">Specificare il metodo utilizzando la classe o interfaccia che lo contiene (`td`), il relativo nome (`szName`) e facoltativamente la firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="ce155-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="ce155-114">Potrebbero esserci più metodi con lo stesso nome in una classe o interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ce155-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="ce155-115">In tal caso, passare la firma del metodo per trovare una corrispondenza univoca.</span><span class="sxs-lookup"><span data-stu-id="ce155-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="ce155-116">La firma è passato a `FindMethod` deve essere stata generata nell'ambito corrente, in quanto le firme sono associate a un particolare ambito.</span><span class="sxs-lookup"><span data-stu-id="ce155-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="ce155-117">Una firma possibile incorporare un token che identifica il tipo di classe o valore di inclusione.</span><span class="sxs-lookup"><span data-stu-id="ce155-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="ce155-118">Il token è un indice nella tabella di TypeDef locale.</span><span class="sxs-lookup"><span data-stu-id="ce155-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="ce155-119">Non è possibile generare una firma in fase di esecuzione all'esterno del contesto dell'ambito corrente e usare come input a quella firma `FindMethod`.</span><span class="sxs-lookup"><span data-stu-id="ce155-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 `FindMethod` <span data-ttu-id="ce155-120">Trova solo i metodi che sono stati definiti direttamente nella classe o interfaccia. metodi ereditati non viene trovato.</span><span class="sxs-lookup"><span data-stu-id="ce155-120">finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce155-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce155-121">Requirements</span></span>  
 <span data-ttu-id="ce155-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce155-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce155-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ce155-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce155-124">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ce155-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ce155-125">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ce155-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ce155-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce155-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="ce155-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ce155-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ce155-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ce155-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
