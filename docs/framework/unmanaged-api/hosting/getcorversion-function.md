---
title: Funzione GetCORVersion
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178186"
---
# <a name="getcorversion-function"></a><span data-ttu-id="68b05-102">Funzione GetCORVersion</span><span class="sxs-lookup"><span data-stu-id="68b05-102">GetCORVersion Function</span></span>
<span data-ttu-id="68b05-103">Restituisce il numero di versione di Common Language Runtime (CLR) in esecuzione nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="68b05-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="68b05-104">Questa funzione è stata deprecata in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="68b05-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68b05-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68b05-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="68b05-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="68b05-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="68b05-107">Puntatore a un buffer in cui CLR restituisce una stringa che specifica la versione del runtime attualmente caricata nel processo.</span><span class="sxs-lookup"><span data-stu-id="68b05-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="68b05-108">La stringa restituita ha lo stesso formato delle stringhe passate a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), ad esempio "v1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="68b05-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="68b05-109">Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriate per la versione più recente del runtime installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="68b05-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="68b05-110">Il numero di`WCHAR`caratteri (s) `pbuffer`che possono essere contenuti in .</span><span class="sxs-lookup"><span data-stu-id="68b05-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="68b05-111">Puntatore al numero di caratteri `pbuffer`effettivamente restituiti in .</span><span class="sxs-lookup"><span data-stu-id="68b05-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="68b05-112">Se `pbuffer` è un puntatore null, il runtime restituisce E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="68b05-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="68b05-113">Se il numero di caratteri è `pbuffer` maggiore della lunghezza di , il runtime restituisce ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="68b05-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68b05-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="68b05-114">Requirements</span></span>  
 <span data-ttu-id="68b05-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68b05-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68b05-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="68b05-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68b05-117">**Biblioteca:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="68b05-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68b05-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68b05-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b05-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68b05-119">See also</span></span>

- [<span data-ttu-id="68b05-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="68b05-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
