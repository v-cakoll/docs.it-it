---
title: Funzione RunDll32ShimW
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa7df47ab55b8dc7ef3f55f5591b44614052bcee
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490134"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="f85cd-102">Funzione RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="f85cd-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="f85cd-103">Esegue il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="f85cd-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="f85cd-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f85cd-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f85cd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f85cd-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f85cd-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f85cd-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="f85cd-107">[in] Handle per una finestra in cui verrà visualizzato l'output del comando.</span><span class="sxs-lookup"><span data-stu-id="f85cd-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="f85cd-108">[in] Handle per la raccolta che contiene il comando.</span><span class="sxs-lookup"><span data-stu-id="f85cd-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="f85cd-109">[in] Stringa che specifica il comando da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f85cd-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="f85cd-110">[in] Valore intero che specifica la modalità di visualizzazione della finestra di output.</span><span class="sxs-lookup"><span data-stu-id="f85cd-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f85cd-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f85cd-111">Requirements</span></span>  
 <span data-ttu-id="f85cd-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f85cd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f85cd-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f85cd-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f85cd-114">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f85cd-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f85cd-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f85cd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85cd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f85cd-116">See also</span></span>

- [<span data-ttu-id="f85cd-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="f85cd-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
