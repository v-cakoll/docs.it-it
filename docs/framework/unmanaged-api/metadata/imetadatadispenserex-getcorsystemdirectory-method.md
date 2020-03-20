---
title: Metodo IMetaDataDispenserEx::GetCORSystemDirectory
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
ms.openlocfilehash: fb673666543bea3df44005ee3b20d311524f51d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175915"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="e2afa-102">Metodo IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="e2afa-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="e2afa-103">Ottiene la directory che contiene il Common Language Runtime (CLR) corrente.</span><span class="sxs-lookup"><span data-stu-id="e2afa-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="e2afa-104">Questo metodo è supportato solo per l'utilizzo da parte di debugger out-of-process.</span><span class="sxs-lookup"><span data-stu-id="e2afa-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="e2afa-105">Se chiamato da un altro componente, restituirà E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e2afa-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2afa-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2afa-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2afa-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2afa-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="e2afa-108">[fuori] Buffer per ricevere il nome della directory.</span><span class="sxs-lookup"><span data-stu-id="e2afa-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="e2afa-109">[in] Dimensione, in byte, `szBuffer`di .</span><span class="sxs-lookup"><span data-stu-id="e2afa-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="e2afa-110">[fuori] Numero di byte effettivamente `szBuffer`restituiti in .</span><span class="sxs-lookup"><span data-stu-id="e2afa-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2afa-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2afa-111">Requirements</span></span>  
 <span data-ttu-id="e2afa-112">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2afa-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2afa-113">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e2afa-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2afa-114">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2afa-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e2afa-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2afa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2afa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2afa-116">See also</span></span>

- [<span data-ttu-id="e2afa-117">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="e2afa-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="e2afa-118">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="e2afa-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
