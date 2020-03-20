---
title: Funzione GetCORSystemDirectory
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178198"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="32c1b-102">Funzione GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="32c1b-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="32c1b-103">Restituisce la directory di installazione di Common Language Runtime (CLR) caricata nel processo.</span><span class="sxs-lookup"><span data-stu-id="32c1b-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="32c1b-104">La directory di installazione è completa, ad esempio, "c:"windows"microsoft.net framework"v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="32c1b-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="32c1b-105">Questa funzione è deprecata.</span><span class="sxs-lookup"><span data-stu-id="32c1b-105">This function is deprecated.</span></span> <span data-ttu-id="32c1b-106">Viene sostituito dal metodo [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) fornito in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="32c1b-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c1b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32c1b-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="32c1b-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="32c1b-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="32c1b-109">[fuori] Buffer in cui il runtime restituisce una stringa contenente il nome completo della directory di installazione per il runtime caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="32c1b-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="32c1b-110">Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriate per la versione più recente del runtime installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="32c1b-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="32c1b-111">[in] Dimensione, in byte, `pbuffer`di .</span><span class="sxs-lookup"><span data-stu-id="32c1b-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="32c1b-112">[fuori] Numero di caratteri restituiti in `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="32c1b-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32c1b-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="32c1b-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="32c1b-114">Non utilizzare questa funzione nei processi che eseguono la versione 4 di CLR.</span><span class="sxs-lookup"><span data-stu-id="32c1b-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="32c1b-115">Se nel computer è installata una versione precedente di CLR, questa funzione restituisce la directory di installazione per tale versione.</span><span class="sxs-lookup"><span data-stu-id="32c1b-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32c1b-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32c1b-116">Requirements</span></span>  
 <span data-ttu-id="32c1b-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32c1b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32c1b-118">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32c1b-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32c1b-119">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="32c1b-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32c1b-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32c1b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c1b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32c1b-121">See also</span></span>

- [<span data-ttu-id="32c1b-122">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="32c1b-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
