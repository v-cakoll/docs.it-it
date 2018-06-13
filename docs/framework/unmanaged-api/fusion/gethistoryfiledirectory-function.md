---
title: Funzione GetHistoryFileDirectory
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba40acf7bfd20897ece4de285fe7a9175be83e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431763"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="3cbd5-102">Funzione GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="3cbd5-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="3cbd5-103">Recupera il percorso della directory della cronologia dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cbd5-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cbd5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3cbd5-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3cbd5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3cbd5-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="3cbd5-106">[out] Buffer contenente il percorso alla directory della cronologia dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3cbd5-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="3cbd5-107">[in, out] La lunghezza del buffer.</span><span class="sxs-lookup"><span data-stu-id="3cbd5-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cbd5-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3cbd5-108">Return Value</span></span>  
 <span data-ttu-id="3cbd5-109">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="3cbd5-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="3cbd5-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="3cbd5-110">Return code</span></span>|<span data-ttu-id="3cbd5-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cbd5-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="3cbd5-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cbd5-112">S_OK</span></span>|<span data-ttu-id="3cbd5-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3cbd5-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="3cbd5-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3cbd5-114">E_INVALIDARG</span></span>|<span data-ttu-id="3cbd5-115">`wzDir` o `pdwSize` è null o la versione stringa non è corretta.</span><span class="sxs-lookup"><span data-stu-id="3cbd5-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cbd5-116">Note</span><span class="sxs-lookup"><span data-stu-id="3cbd5-116">Remarks</span></span>  
 <span data-ttu-id="3cbd5-117">Al termine, il `pdwSize` argomento è impostato sulla lunghezza della stringa di percorso.</span><span class="sxs-lookup"><span data-stu-id="3cbd5-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cbd5-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3cbd5-118">Requirements</span></span>  
 <span data-ttu-id="3cbd5-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cbd5-120">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3cbd5-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3cbd5-121">**Libreria:** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="3cbd5-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="3cbd5-122">Utilizzare il file Fusion.dll anziché Mscorwks.dll per garantire che la versione corretta di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3cbd5-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="3cbd5-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbd5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cbd5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cbd5-124">See Also</span></span>  
 [<span data-ttu-id="3cbd5-125">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="3cbd5-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="3cbd5-126">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="3cbd5-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [<span data-ttu-id="3cbd5-127">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="3cbd5-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
