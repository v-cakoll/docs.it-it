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
ms.openlocfilehash: cf580f6d3fb18e729f3eca300aa817036eb61e4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443430"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="c035d-102">Metodo IMetaDataDispenserEx::GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="c035d-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="c035d-103">Ottiene la directory contenente corrente common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c035d-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="c035d-104">Questo metodo è supportato solo per uso dai debugger out-of-process.</span><span class="sxs-lookup"><span data-stu-id="c035d-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="c035d-105">Se chiamato da un altro componente, verrà restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c035d-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c035d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c035d-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c035d-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="c035d-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="c035d-108">[out] Il buffer per ricevere il nome della directory.</span><span class="sxs-lookup"><span data-stu-id="c035d-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="c035d-109">[in] Le dimensioni, in byte, di `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="c035d-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="c035d-110">[out] Il numero di byte effettivamente restituiti nella `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="c035d-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c035d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c035d-111">Requirements</span></span>  
 <span data-ttu-id="c035d-112">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c035d-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c035d-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c035d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c035d-114">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c035d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c035d-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c035d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c035d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c035d-116">See Also</span></span>  
 [<span data-ttu-id="c035d-117">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="c035d-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="c035d-118">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="c035d-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
