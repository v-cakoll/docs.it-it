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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 40631a15bd07b5aa54488e5d3b99cee751e2e0bd
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748336"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="45520-102">Metodo IMetaDataImport::GetMemberProps</span><span class="sxs-lookup"><span data-stu-id="45520-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="45520-103">Ottiene le informazioni archiviate nei metadati per una definizione di membro specificato, inclusi il nome, la firma binaria e indirizzo virtuale relativo, del <xref:System.Type> membro a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="45520-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="45520-104">Si tratta di un metodo di supporto semplice: se *mb* viene quindi un MethodDef **GetMethodProps** viene chiamato; se *mb* è FieldDef, quindi **GetFieldProps** viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="45520-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="45520-105">Vedere questi altri metodi per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="45520-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="45520-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45520-106">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="45520-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="45520-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="45520-108">[in] Il token che fa riferimento al membro per ottenere i metadati associati.</span><span class="sxs-lookup"><span data-stu-id="45520-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="45520-109">[out] Puntatore al token di metadati che rappresenta la classe del membro.</span><span class="sxs-lookup"><span data-stu-id="45520-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="45520-110">[out] Il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="45520-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="45520-111">[in] La dimensione in caratteri "wide" del `szMember` buffer.</span><span class="sxs-lookup"><span data-stu-id="45520-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="45520-112">[out] Dimensione in caratteri "wide" del nome restituito.</span><span class="sxs-lookup"><span data-stu-id="45520-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="45520-113">[out] I valori di flag applicati al membro.</span><span class="sxs-lookup"><span data-stu-id="45520-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="45520-114">[out] Un puntatore per la firma binaria dei metadati del membro.</span><span class="sxs-lookup"><span data-stu-id="45520-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="45520-115">[out] La dimensione in byte di `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="45520-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="45520-116">[out] Un puntatore all'indirizzo virtuale relativo del membro.</span><span class="sxs-lookup"><span data-stu-id="45520-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="45520-117">[out] Flag di implementazione del metodo associato al membro.</span><span class="sxs-lookup"><span data-stu-id="45520-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="45520-118">[out] Un flag che contrassegna un <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="45520-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="45520-119">È uno del `ELEMENT_TYPE_*` valori.</span><span class="sxs-lookup"><span data-stu-id="45520-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="45520-120">[out] Un valore stringa costante restituito da questo membro.</span><span class="sxs-lookup"><span data-stu-id="45520-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="45520-121">[out] La dimensione in caratteri della `ppValue`, oppure zero se `ppValue` non contiene una stringa.</span><span class="sxs-lookup"><span data-stu-id="45520-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45520-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45520-122">Requirements</span></span>  
 <span data-ttu-id="45520-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45520-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45520-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="45520-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45520-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="45520-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45520-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45520-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45520-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45520-127">See also</span></span>
- [<span data-ttu-id="45520-128">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="45520-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="45520-129">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="45520-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
