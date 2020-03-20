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
ms.openlocfilehash: 5af59e158a34b06d304a98db1dfaa46585b22eb6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177199"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="6c549-102">Metodo IMetaDataImport::GetSigFromToken</span><span class="sxs-lookup"><span data-stu-id="6c549-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="6c549-103">Ottiene la firma binaria dei metadati associata al token specificato.</span><span class="sxs-lookup"><span data-stu-id="6c549-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c549-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c549-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSigFromToken (
   [in]   mdSignature        mdSig,
   [out]  PCCOR_SIGNATURE    *ppvSig,
   [out]  ULONG              *pcbSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c549-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c549-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="6c549-106">[in] Token per cui restituire la firma di metadati binari.</span><span class="sxs-lookup"><span data-stu-id="6c549-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="6c549-107">[fuori] Puntatore alla firma dei metadati restituita.</span><span class="sxs-lookup"><span data-stu-id="6c549-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="6c549-108">[fuori] Dimensione in byte della firma dei metadati binari.</span><span class="sxs-lookup"><span data-stu-id="6c549-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c549-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c549-109">Requirements</span></span>  
 <span data-ttu-id="6c549-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c549-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c549-111">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6c549-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c549-112">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c549-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c549-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c549-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c549-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c549-114">See also</span></span>

- [<span data-ttu-id="6c549-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6c549-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6c549-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6c549-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
