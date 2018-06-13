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
ms.openlocfilehash: d93763da2afbbdb1e738c802ba172e9f16e5f7af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448458"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="bd9b2-102">Metodo IMetaDataImport::GetMemberProps</span><span class="sxs-lookup"><span data-stu-id="bd9b2-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="bd9b2-103">Ottiene informazioni sui metadati, inclusi il nome, la firma binaria e l'indirizzo virtuale relativo, del <xref:System.Type> membro a cui fa riferimento il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-103">Gets metadata information, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd9b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd9b2-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="bd9b2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd9b2-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="bd9b2-106">[in] Token che fa riferimento al membro per ottenere i metadati associati.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-106">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="bd9b2-107">[out] Puntatore al token di metadati che rappresenta la classe del membro.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-107">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="bd9b2-108">[out] Il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-108">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="bd9b2-109">[in] La dimensione in caratteri "wide" del `szMember` buffer.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-109">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="bd9b2-110">[out] Dimensione in caratteri "wide" del nome restituito.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-110">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="bd9b2-111">[out] Eventuali valori di flag applicati al membro.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-111">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="bd9b2-112">[out] Un puntatore per la firma binaria dei metadati del membro.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-112">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="bd9b2-113">[out] Le dimensioni in byte di `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="bd9b2-114">[out] Un puntatore all'indirizzo virtuale relativo del membro.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-114">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="bd9b2-115">[out] Flag di implementazione del metodo associato al membro.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-115">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="bd9b2-116">[out] Flag che contrassegna un <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-116">[out] A flag that marks a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="bd9b2-117">[out] Valore stringa costante restituito da questo membro.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-117">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="bd9b2-118">[out] La dimensione in caratteri di `ppValue`, oppure zero se `ppValue` non contiene una stringa.</span><span class="sxs-lookup"><span data-stu-id="bd9b2-118">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd9b2-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd9b2-119">Requirements</span></span>  
 <span data-ttu-id="bd9b2-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd9b2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd9b2-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bd9b2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd9b2-122">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bd9b2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd9b2-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd9b2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd9b2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd9b2-124">See Also</span></span>  
 [<span data-ttu-id="bd9b2-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="bd9b2-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="bd9b2-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="bd9b2-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
