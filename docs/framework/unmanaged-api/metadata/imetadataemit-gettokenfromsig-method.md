---
title: Metodo IMetaDataEmit::GetTokenFromSig
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
ms.openlocfilehash: 740dad54bc3a79ff546176abdc35487d89ed8f44
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009249"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="cedf3-102">Metodo IMetaDataEmit::GetTokenFromSig</span><span class="sxs-lookup"><span data-stu-id="cedf3-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="cedf3-103">Ottiene un token per la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="cedf3-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cedf3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cedf3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromSig (
    [in]  PCCOR_SIGNATURE pvSig,
    [in]  ULONG       cbSig,
    [out] mdSignature *pmsig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cedf3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cedf3-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="cedf3-106">in Firma da salvare in modo permanente e archiviare.</span><span class="sxs-lookup"><span data-stu-id="cedf3-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="cedf3-107">in Numero di byte in `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="cedf3-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="cedf3-108">out `mdSignature`Token assegnato.</span><span class="sxs-lookup"><span data-stu-id="cedf3-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cedf3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cedf3-109">Requirements</span></span>  
 <span data-ttu-id="cedf3-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cedf3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cedf3-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cedf3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cedf3-112">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cedf3-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cedf3-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cedf3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cedf3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cedf3-114">See also</span></span>

- [<span data-ttu-id="cedf3-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cedf3-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="cedf3-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cedf3-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
