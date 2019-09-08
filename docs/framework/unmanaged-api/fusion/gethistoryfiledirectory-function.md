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
ms.openlocfilehash: adbbf94dc36c6d82360ed532b283cd666a1a52ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796858"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="ff4db-102">Funzione GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="ff4db-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="ff4db-103">Recupera il percorso della directory della cronologia dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ff4db-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff4db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff4db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff4db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff4db-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="ff4db-106">out Buffer che consente di memorizzare il percorso della directory della cronologia dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ff4db-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="ff4db-107">[in, out] Lunghezza del buffer.</span><span class="sxs-lookup"><span data-stu-id="ff4db-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff4db-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ff4db-108">Return Value</span></span>  
 <span data-ttu-id="ff4db-109">Questo metodo restituisce i codici di errore COM standard, definiti nel file WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="ff4db-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="ff4db-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="ff4db-110">Return code</span></span>|<span data-ttu-id="ff4db-111">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="ff4db-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ff4db-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff4db-112">S_OK</span></span>|<span data-ttu-id="ff4db-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ff4db-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="ff4db-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ff4db-114">E_INVALIDARG</span></span>|<span data-ttu-id="ff4db-115">`wzDir`o `pdwSize` è null oppure la stringa di versione non è corretta.</span><span class="sxs-lookup"><span data-stu-id="ff4db-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff4db-116">Note</span><span class="sxs-lookup"><span data-stu-id="ff4db-116">Remarks</span></span>  
 <span data-ttu-id="ff4db-117">Al termine dell'operazione, `pdwSize` l'argomento viene impostato sulla lunghezza della stringa di percorso.</span><span class="sxs-lookup"><span data-stu-id="ff4db-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff4db-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff4db-118">Requirements</span></span>  
 <span data-ttu-id="ff4db-119">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff4db-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff4db-120">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ff4db-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ff4db-121">**Libreria** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="ff4db-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="ff4db-122">Usare Fusion. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff4db-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ff4db-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff4db-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4db-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff4db-124">See also</span></span>

- [<span data-ttu-id="ff4db-125">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="ff4db-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="ff4db-126">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="ff4db-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="ff4db-127">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="ff4db-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
