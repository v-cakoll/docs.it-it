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
ms.openlocfilehash: 00693f1a87334620442e8865e76183b2dab68878
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503615"
---
# <a name="imetadataimportgetmemberrefprops-method"></a><span data-ttu-id="2d372-102">Metodo IMetaDataImport::GetMemberRefProps</span><span class="sxs-lookup"><span data-stu-id="2d372-102">IMetaDataImport::GetMemberRefProps Method</span></span>
<span data-ttu-id="2d372-103">Ottiene i metadati associati al membro a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="2d372-103">Gets metadata associated with the member referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d372-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d372-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2d372-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2d372-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="2d372-106">in Token MemberRef per il quale restituire i metadati associati.</span><span class="sxs-lookup"><span data-stu-id="2d372-106">[in] The MemberRef token to return associated metadata for.</span></span>  
  
 `ptk`  
 <span data-ttu-id="2d372-107">out Token TypeDef o TypeRef o TypeSpec che rappresenta la classe che dichiara il membro o un token ModuleRef che rappresenta la classe modulo che dichiara il membro o un MethodDef che rappresenta il membro.</span><span class="sxs-lookup"><span data-stu-id="2d372-107">[out] A TypeDef or TypeRef, or TypeSpec token that represents the class that declares the member, or a ModuleRef token that represents the module class that declares the member, or a MethodDef that represents the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="2d372-108">out Buffer di stringa per il nome del membro.</span><span class="sxs-lookup"><span data-stu-id="2d372-108">[out] A string buffer for the member's name.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="2d372-109">in Dimensioni richieste in caratteri wide di `szMember` .</span><span class="sxs-lookup"><span data-stu-id="2d372-109">[in] The requested size in wide characters of `szMember`.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="2d372-110">out Dimensione restituita in caratteri wide di `szMember` .</span><span class="sxs-lookup"><span data-stu-id="2d372-110">[out] The returned size in wide characters of `szMember`.</span></span>  
  
 `ppvSibBlob`  
 <span data-ttu-id="2d372-111">out Puntatore alla firma dei metadati binaria per il membro.</span><span class="sxs-lookup"><span data-stu-id="2d372-111">[out] A pointer to the binary metadata signature for the member.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="2d372-112">out Dimensioni in byte di `ppvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="2d372-112">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d372-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d372-113">Requirements</span></span>  
 <span data-ttu-id="2d372-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d372-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d372-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2d372-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2d372-116">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2d372-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2d372-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d372-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d372-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d372-118">See also</span></span>

- [<span data-ttu-id="2d372-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2d372-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2d372-120">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2d372-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
