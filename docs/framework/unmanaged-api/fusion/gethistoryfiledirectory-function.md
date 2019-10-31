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
ms.openlocfilehash: 1aabfad14ee2eb35916bbf115631602276cd1fc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109899"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="7f21d-102">Funzione GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="7f21d-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="7f21d-103">Recupera il percorso della directory della cronologia dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f21d-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f21d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f21d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f21d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f21d-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="7f21d-106">out Buffer che consente di memorizzare il percorso della directory della cronologia dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f21d-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="7f21d-107">[in, out] Lunghezza del buffer.</span><span class="sxs-lookup"><span data-stu-id="7f21d-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f21d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7f21d-108">Return Value</span></span>  
 <span data-ttu-id="7f21d-109">Questo metodo restituisce i codici di errore COM standard, definiti nel file WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="7f21d-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="7f21d-110">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="7f21d-110">Return code</span></span>|<span data-ttu-id="7f21d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f21d-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7f21d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f21d-112">S_OK</span></span>|<span data-ttu-id="7f21d-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7f21d-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="7f21d-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7f21d-114">E_INVALIDARG</span></span>|<span data-ttu-id="7f21d-115">`wzDir` o `pdwSize` è null o la stringa di versione non è corretta.</span><span class="sxs-lookup"><span data-stu-id="7f21d-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f21d-116">Note</span><span class="sxs-lookup"><span data-stu-id="7f21d-116">Remarks</span></span>  
 <span data-ttu-id="7f21d-117">Al termine dell'operazione, l'argomento `pdwSize` viene impostato sulla lunghezza della stringa di percorso.</span><span class="sxs-lookup"><span data-stu-id="7f21d-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f21d-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f21d-118">Requirements</span></span>  
 <span data-ttu-id="7f21d-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f21d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f21d-120">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7f21d-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7f21d-121">**Libreria:** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="7f21d-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="7f21d-122">Usare Fusion. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f21d-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7f21d-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f21d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f21d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f21d-124">See also</span></span>

- [<span data-ttu-id="7f21d-125">Funzione CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="7f21d-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="7f21d-126">Funzione NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="7f21d-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="7f21d-127">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="7f21d-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
