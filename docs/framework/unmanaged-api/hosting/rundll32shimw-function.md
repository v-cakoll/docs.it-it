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
ms.openlocfilehash: 18247a947449ea5fd19f1882031b598086332742
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441740"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="34b8e-102">Funzione RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="34b8e-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="34b8e-103">Esegue il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="34b8e-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="34b8e-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34b8e-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34b8e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34b8e-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34b8e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="34b8e-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="34b8e-107">[in] Un handle a una finestra in cui verrà visualizzato l'output del comando.</span><span class="sxs-lookup"><span data-stu-id="34b8e-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="34b8e-108">[in] Handle per la raccolta che contiene il comando.</span><span class="sxs-lookup"><span data-stu-id="34b8e-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="34b8e-109">[in] Stringa che specifica il comando da eseguire.</span><span class="sxs-lookup"><span data-stu-id="34b8e-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="34b8e-110">[in] Valore intero che specifica la modalità di visualizzazione della finestra di output.</span><span class="sxs-lookup"><span data-stu-id="34b8e-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34b8e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34b8e-111">Requirements</span></span>  
 <span data-ttu-id="34b8e-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34b8e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34b8e-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="34b8e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34b8e-114">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="34b8e-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34b8e-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34b8e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34b8e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34b8e-116">See Also</span></span>  
 [<span data-ttu-id="34b8e-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="34b8e-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
