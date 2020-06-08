---
title: Metodo IMetaDataImport::GetSigFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
ms.openlocfilehash: d795f90c458b7fcf1a191b2763ac5f5bb55fb438
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490898"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="4e614-102">Metodo IMetaDataImport::GetSigFromToken</span><span class="sxs-lookup"><span data-stu-id="4e614-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="4e614-103">Ottiene la firma binaria dei metadati associata al token specificato.</span><span class="sxs-lookup"><span data-stu-id="4e614-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e614-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e614-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e614-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e614-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="4e614-106">in Token per il quale restituire la firma dei metadati binari.</span><span class="sxs-lookup"><span data-stu-id="4e614-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="4e614-107">out Puntatore alla firma dei metadati restituita.</span><span class="sxs-lookup"><span data-stu-id="4e614-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="4e614-108">out Dimensioni in byte della firma dei metadati binari.</span><span class="sxs-lookup"><span data-stu-id="4e614-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e614-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e614-109">Requirements</span></span>  
 <span data-ttu-id="4e614-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e614-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e614-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4e614-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e614-112">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e614-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e614-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e614-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e614-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e614-114">See also</span></span>

- [<span data-ttu-id="4e614-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4e614-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4e614-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4e614-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
