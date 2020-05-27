---
title: Metodo IMetaDataEmit::DefineMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
ms.openlocfilehash: 576f4561ed782f091840ac378831110a1bfef9c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004692"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="5588a-102">Metodo IMetaDataEmit::DefineMemberRef</span><span class="sxs-lookup"><span data-stu-id="5588a-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="5588a-103">Definisce un riferimento a un membro di un modulo esterno all'ambito corrente e ottiene un token per la definizione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5588a-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5588a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5588a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5588a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5588a-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="5588a-106">in Token per la classe o l'interfaccia del membro di destinazione, se il membro non è globale; Se il membro è globale, il `mdModuleRef` token per l'altro file.</span><span class="sxs-lookup"><span data-stu-id="5588a-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="5588a-107">in Nome del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5588a-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5588a-108">in Firma del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5588a-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="5588a-109">in Numero di byte in `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="5588a-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="5588a-110">out `mdMemberRef`Token assegnato.</span><span class="sxs-lookup"><span data-stu-id="5588a-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5588a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5588a-111">Requirements</span></span>  
 <span data-ttu-id="5588a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5588a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5588a-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5588a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5588a-114">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5588a-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5588a-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5588a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5588a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5588a-116">See also</span></span>

- [<span data-ttu-id="5588a-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5588a-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5588a-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5588a-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
