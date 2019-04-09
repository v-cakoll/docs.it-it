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
ms.openlocfilehash: a2c431abb7a4a872454b9c2689ee195ed36ef236
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177014"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="df63e-102">Metodo IMetaDataImport::GetMemberRefProps</span><span class="sxs-lookup"><span data-stu-id="df63e-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="df63e-103">Ottiene i metadati associati al membro a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="df63e-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df63e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df63e-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="df63e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="df63e-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="df63e-106">[in] Il token MemberRef per restituire i metadati associati.</span><span class="sxs-lookup"><span data-stu-id="df63e-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="df63e-107">[out] Token TypeDef o TypeRef o TypeSpec che rappresenta la classe che dichiara il membro o un token ModuleRef che rappresenta la classe di modulo che dichiara il membro o un MethodDef che rappresenta il membro.</span><span class="sxs-lookup"><span data-stu-id="df63e-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="df63e-108">[out] Un buffer di stringa per il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="df63e-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="df63e-109">[in] Le dimensioni richieste in caratteri wide di `szMember`.</span><span class="sxs-lookup"><span data-stu-id="df63e-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="df63e-110">[out] Le dimensioni restituite in caratteri wide di `szMember`.</span><span class="sxs-lookup"><span data-stu-id="df63e-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="df63e-111">[out] Un puntatore per la firma binaria dei metadati per il membro.</span><span class="sxs-lookup"><span data-stu-id="df63e-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="df63e-112">[out] La dimensione in byte di `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="df63e-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df63e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df63e-113">Requirements</span></span>  
 <span data-ttu-id="df63e-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df63e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df63e-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="df63e-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df63e-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="df63e-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="df63e-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="df63e-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df63e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df63e-118">See also</span></span>

- [<span data-ttu-id="df63e-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="df63e-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="df63e-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="df63e-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
