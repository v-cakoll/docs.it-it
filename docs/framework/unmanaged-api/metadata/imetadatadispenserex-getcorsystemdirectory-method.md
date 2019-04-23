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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3dbfca942d61cd5667293d11f358f06bd000fa2e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118001"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="05bf5-102">Metodo IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="05bf5-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="05bf5-103">Ottiene la directory che contiene corrente common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="05bf5-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="05bf5-104">Questo metodo è supportato solo per uso dai debugger out-of-process.</span><span class="sxs-lookup"><span data-stu-id="05bf5-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="05bf5-105">Se chiamato da un altro componente, verrà restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="05bf5-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05bf5-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05bf5-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05bf5-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="05bf5-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="05bf5-108">[out] Il buffer per ricevere il nome della directory.</span><span class="sxs-lookup"><span data-stu-id="05bf5-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="05bf5-109">[in] Le dimensioni, in byte, di `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="05bf5-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="05bf5-110">[out] Il numero di byte effettivamente restituiti nella `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="05bf5-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05bf5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05bf5-111">Requirements</span></span>  
 <span data-ttu-id="05bf5-112">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05bf5-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05bf5-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="05bf5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05bf5-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="05bf5-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05bf5-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05bf5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05bf5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05bf5-116">See also</span></span>

- [<span data-ttu-id="05bf5-117">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="05bf5-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="05bf5-118">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="05bf5-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
