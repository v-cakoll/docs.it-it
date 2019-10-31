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
ms.openlocfilehash: d39e15a2ba71ba0c0147482259f5618dcb5d298b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192099"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="fd087-102">Funzione CallFunctionShim</span><span class="sxs-lookup"><span data-stu-id="fd087-102">CallFunctionShim Function</span></span>
<span data-ttu-id="fd087-103">Esegue una chiamata alla funzione con il nome e i parametri specificati nella libreria specificata.</span><span class="sxs-lookup"><span data-stu-id="fd087-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="fd087-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fd087-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd087-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd087-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fd087-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd087-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="fd087-107">in Nome della libreria che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="fd087-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="fd087-108">in Nome della funzione.</span><span class="sxs-lookup"><span data-stu-id="fd087-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="fd087-109">in Primo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="fd087-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="fd087-110">in Secondo argomento da passare alla funzione.</span><span class="sxs-lookup"><span data-stu-id="fd087-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="fd087-111">in Versione della raccolta che contiene la funzione.</span><span class="sxs-lookup"><span data-stu-id="fd087-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="fd087-112">in Riservato per usi futuri.</span><span class="sxs-lookup"><span data-stu-id="fd087-112">[in] Reserved for future use.</span></span> <span data-ttu-id="fd087-113">Passare zero in questo parametro.</span><span class="sxs-lookup"><span data-stu-id="fd087-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd087-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd087-114">Requirements</span></span>  
 <span data-ttu-id="fd087-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd087-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd087-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd087-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd087-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fd087-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd087-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd087-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd087-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd087-119">See also</span></span>

- [<span data-ttu-id="fd087-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="fd087-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
