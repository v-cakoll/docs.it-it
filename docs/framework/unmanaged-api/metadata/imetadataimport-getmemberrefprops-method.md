---
title: Metodo IMetaDataImport::GetMemberRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fadc54d74ce6027bd021e148a14cb0c432eb41fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782348"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="98dde-102">Metodo IMetaDataImport::GetMemberRefProps</span><span class="sxs-lookup"><span data-stu-id="98dde-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="98dde-103">Ottiene i metadati associati al membro a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="98dde-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98dde-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98dde-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98dde-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="98dde-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="98dde-106">[in] Il token MemberRef per restituire i metadati associati.</span><span class="sxs-lookup"><span data-stu-id="98dde-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="98dde-107">[out] Token TypeDef o TypeRef o TypeSpec che rappresenta la classe che dichiara il membro o un token ModuleRef che rappresenta la classe di modulo che dichiara il membro o un MethodDef che rappresenta il membro.</span><span class="sxs-lookup"><span data-stu-id="98dde-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="98dde-108">[out] Un buffer di stringa per il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="98dde-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="98dde-109">[in] Le dimensioni richieste in caratteri wide di `szMember`.</span><span class="sxs-lookup"><span data-stu-id="98dde-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="98dde-110">[out] Le dimensioni restituite in caratteri wide di `szMember`.</span><span class="sxs-lookup"><span data-stu-id="98dde-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="98dde-111">[out] Un puntatore per la firma binaria dei metadati per il membro.</span><span class="sxs-lookup"><span data-stu-id="98dde-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="98dde-112">[out] La dimensione in byte di `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="98dde-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98dde-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98dde-113">Requirements</span></span>  
 <span data-ttu-id="98dde-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98dde-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98dde-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="98dde-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98dde-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="98dde-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98dde-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98dde-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98dde-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98dde-118">See also</span></span>

- [<span data-ttu-id="98dde-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="98dde-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="98dde-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="98dde-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
