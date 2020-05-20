---
title: Funzione CallFunctionShim
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
ms.openlocfilehash: e8945d40a3761ec51a73a8ae90ddc1d84ccab651
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616866"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="e2b4c-102">Funzione CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="e2b4c-102">CallFunctionShim Function</span></span>
<span data-ttu-id="e2b4c-103">Esegue una chiamata alla funzione con il nome e i parametri specificati nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="e2b4c-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="e2b4c-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e2b4c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b4c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2b4c-105">Syntax</span></span>  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2b4c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2b4c-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="e2b4c-107">in Nome della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="e2b4c-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="e2b4c-108">in Nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="e2b4c-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="e2b4c-109">in Primo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="e2b4c-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="e2b4c-110">in Secondo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="e2b4c-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="e2b4c-111">in Versione della raccolta che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="e2b4c-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e2b4c-112">[in] Riservato per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="e2b4c-112">[in] Reserved for future use.</span></span> <span data-ttu-id="e2b4c-113">Passare zero in questo parametro.</span><span class="sxs-lookup"><span data-stu-id="e2b4c-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2b4c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2b4c-114">Requirements</span></span>  
 <span data-ttu-id="e2b4c-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2b4c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2b4c-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e2b4c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2b4c-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e2b4c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2b4c-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2b4c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b4c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2b4c-119">See also</span></span>

- [<span data-ttu-id="e2b4c-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="e2b4c-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
