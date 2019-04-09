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
ms.openlocfilehash: b60dde31707175a27d2dc6c50484d6089adaeaa6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229625"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="7a209-102">Funzione GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="7a209-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="7a209-103">Recupera il percorso della directory della cronologia dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7a209-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a209-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a209-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a209-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a209-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="7a209-106">[out] Buffer contenente il percorso della directory della cronologia dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7a209-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="7a209-107">[in, out] La lunghezza del buffer.</span><span class="sxs-lookup"><span data-stu-id="7a209-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a209-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7a209-108">Return Value</span></span>  
 <span data-ttu-id="7a209-109">Questo metodo restituisce codici di errore COM standard, come definito nel file Winerror h oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="7a209-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="7a209-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="7a209-110">Return code</span></span>|<span data-ttu-id="7a209-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7a209-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7a209-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a209-112">S_OK</span></span>|<span data-ttu-id="7a209-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7a209-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="7a209-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7a209-114">E_INVALIDARG</span></span>|`wzDir` <span data-ttu-id="7a209-115">o `pdwSize` è null o una versione stringa non è corretta.</span><span class="sxs-lookup"><span data-stu-id="7a209-115">or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a209-116">Note</span><span class="sxs-lookup"><span data-stu-id="7a209-116">Remarks</span></span>  
 <span data-ttu-id="7a209-117">Al termine, il `pdwSize` argomento è impostato per la lunghezza della stringa di percorso.</span><span class="sxs-lookup"><span data-stu-id="7a209-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a209-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a209-118">Requirements</span></span>  
 <span data-ttu-id="7a209-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a209-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a209-120">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7a209-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7a209-121">**Libreria:** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="7a209-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="7a209-122">Usare Fusion. dll invece di Mscorwks. dll per verificare che da usare come destinazione la versione corretta di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7a209-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 **<span data-ttu-id="7a209-123">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7a209-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7a209-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a209-124">See also</span></span>

- [<span data-ttu-id="7a209-125">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="7a209-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="7a209-126">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="7a209-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [<span data-ttu-id="7a209-127">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="7a209-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
