---
title: Metodo IMetaDataImport::GetMemberProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177222"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="1e7f9-102">Metodo IMetaDataImport::GetMemberProps</span><span class="sxs-lookup"><span data-stu-id="1e7f9-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="1e7f9-103">Ottiene le informazioni archiviate nei metadati per una definizione di membro specificata, inclusi il nome, la firma binaria e l'indirizzo <xref:System.Type> virtuale relativo, del membro a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="1e7f9-104">Questo è un metodo helper semplice: se *mb* è un MethodDef, quindi **GetMethodProps** viene chiamato; se *mb* è un FieldDef, quindi **GetFieldProps** viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="1e7f9-105">Vedere questi altri metodi per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-105">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1e7f9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e7f9-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e7f9-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e7f9-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="1e7f9-108">[in] Token che fa riferimento al membro per cui ottenere i metadati associati.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="1e7f9-109">[fuori] Puntatore al token di metadati che rappresenta la classe del membro.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="1e7f9-110">[fuori] Nome del membro.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="1e7f9-111">[in] Dimensione in caratteri di `szMember` tipo "wide" del buffer.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="1e7f9-112">[fuori] Dimensione in caratteri di tipo "wide" del nome restituito.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="1e7f9-113">[fuori] Eventuali valori di flag applicati al membro.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="1e7f9-114">[fuori] Puntatore alla firma dei metadati binari del membro.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="1e7f9-115">[fuori] Dimensione in byte `ppvSigBlob`di .</span><span class="sxs-lookup"><span data-stu-id="1e7f9-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="1e7f9-116">[fuori] Puntatore all'indirizzo virtuale relativo del membro.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="1e7f9-117">[fuori] Qualsiasi flag di implementazione del metodo associato al membro.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="1e7f9-118">[fuori] Una bandiera che <xref:System.ValueType>contrassegna un oggetto .</span><span class="sxs-lookup"><span data-stu-id="1e7f9-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="1e7f9-119">È uno dei `ELEMENT_TYPE_*` valori.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="1e7f9-120">[fuori] Valore stringa costante restituito da questo membro.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="1e7f9-121">[fuori] La dimensione in `ppValue`caratteri di `ppValue` , o zero se non contiene una stringa.</span><span class="sxs-lookup"><span data-stu-id="1e7f9-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e7f9-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e7f9-122">Requirements</span></span>  
 <span data-ttu-id="1e7f9-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e7f9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e7f9-124">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1e7f9-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e7f9-125">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e7f9-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e7f9-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e7f9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7f9-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e7f9-127">See also</span></span>

- [<span data-ttu-id="1e7f9-128">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1e7f9-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1e7f9-129">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1e7f9-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
