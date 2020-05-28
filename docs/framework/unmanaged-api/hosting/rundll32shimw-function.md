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
ms.openlocfilehash: 90304eb94e6f53d3132c97f5ababdc45f6053d7c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006571"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="f36a8-102">Funzione RunDll32ShimW</span><span class="sxs-lookup"><span data-stu-id="f36a8-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="f36a8-103">Esegue il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="f36a8-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="f36a8-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f36a8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f36a8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f36a8-105">Syntax</span></span>  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f36a8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f36a8-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="f36a8-107">in Handle per una finestra in cui verrà visualizzato l'output del comando.</span><span class="sxs-lookup"><span data-stu-id="f36a8-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="f36a8-108">in Handle per la raccolta che contiene il comando.</span><span class="sxs-lookup"><span data-stu-id="f36a8-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="f36a8-109">in Stringa che specifica il comando da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f36a8-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="f36a8-110">in Integer che specifica la modalità di visualizzazione per la finestra di output.</span><span class="sxs-lookup"><span data-stu-id="f36a8-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f36a8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f36a8-111">Requirements</span></span>  
 <span data-ttu-id="f36a8-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f36a8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f36a8-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f36a8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f36a8-114">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f36a8-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f36a8-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f36a8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f36a8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f36a8-116">See also</span></span>

- [<span data-ttu-id="f36a8-117">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="f36a8-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
