---
title: Metodo IMetaDataEmit::GetTokenFromTypeSpec
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 1cd09fe785bb37c892417ddbf1efaaaa90e121bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009236"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="0116b-102">Metodo IMetaDataEmit::GetTokenFromTypeSpec</span><span class="sxs-lookup"><span data-stu-id="0116b-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="0116b-103">Ottiene un token di metadati per il tipo con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="0116b-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0116b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0116b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0116b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0116b-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="0116b-106">in Firma da definire.</span><span class="sxs-lookup"><span data-stu-id="0116b-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="0116b-107">in Numero di byte in `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="0116b-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="0116b-108">out `mdTypeSpec`Token assegnato.</span><span class="sxs-lookup"><span data-stu-id="0116b-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0116b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0116b-109">Requirements</span></span>  
 <span data-ttu-id="0116b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0116b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0116b-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0116b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0116b-112">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0116b-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0116b-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0116b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0116b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0116b-114">See also</span></span>

- [<span data-ttu-id="0116b-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0116b-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="0116b-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0116b-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
