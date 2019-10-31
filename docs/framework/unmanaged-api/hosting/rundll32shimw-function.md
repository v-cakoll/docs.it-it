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
ms.openlocfilehash: e661bd82ecf6d804e852cca4a4478084edf303c5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141494"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="64788-102">Funzione RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="64788-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="64788-103">Esegue il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="64788-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="64788-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="64788-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64788-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64788-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64788-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="64788-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="64788-107">in Handle per una finestra in cui verrà visualizzato l'output del comando.</span><span class="sxs-lookup"><span data-stu-id="64788-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="64788-108">in Handle per la raccolta che contiene il comando.</span><span class="sxs-lookup"><span data-stu-id="64788-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="64788-109">in Stringa che specifica il comando da eseguire.</span><span class="sxs-lookup"><span data-stu-id="64788-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="64788-110">in Integer che specifica la modalità di visualizzazione per la finestra di output.</span><span class="sxs-lookup"><span data-stu-id="64788-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64788-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64788-111">Requirements</span></span>  
 <span data-ttu-id="64788-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64788-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64788-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="64788-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64788-114">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="64788-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64788-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64788-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64788-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64788-116">See also</span></span>

- [<span data-ttu-id="64788-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="64788-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
