---
title: Metodo IMetaDataEmit::SetFieldRVA
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
ms.openlocfilehash: 7648a1b3d219ee5d2b1ddc6b26f7b65c9ac85105
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175642"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="918ef-102">Metodo IMetaDataEmit::SetFieldRVA</span><span class="sxs-lookup"><span data-stu-id="918ef-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="918ef-103">Imposta un valore di variabile globale per l'indirizzo virtuale relativo del campo a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="918ef-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="918ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="918ef-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (
    [in]  mdFieldDef  fd,
    [in]  ULONG       ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="918ef-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="918ef-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="918ef-106">[in] Token per il campo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="918ef-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="918ef-107">[in] Indirizzo di un codice o di un'area dati.</span><span class="sxs-lookup"><span data-stu-id="918ef-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="918ef-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="918ef-108">Requirements</span></span>  
 <span data-ttu-id="918ef-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="918ef-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="918ef-110">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="918ef-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="918ef-111">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="918ef-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="918ef-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="918ef-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="918ef-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="918ef-113">See also</span></span>

- [<span data-ttu-id="918ef-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="918ef-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="918ef-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="918ef-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
