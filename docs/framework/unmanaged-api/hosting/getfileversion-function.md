---
title: Funzione GetFileVersion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
ms.openlocfilehash: f197c8802bd9e55391b3e3e20c64398736070a16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136327"
---
# <a name="getfileversion-function"></a><span data-ttu-id="d8024-102">Funzione GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="d8024-102">GetFileVersion Function</span></span>
<span data-ttu-id="d8024-103">Ottiene le informazioni sulla versione di Common Language Runtime (CLR) del file specificato, utilizzando il buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="d8024-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="d8024-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d8024-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8024-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8024-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8024-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8024-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="d8024-107">in Percorso del file da esaminare.</span><span class="sxs-lookup"><span data-stu-id="d8024-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="d8024-108">[in, out] Buffer allocato per le informazioni sulla versione restituite.</span><span class="sxs-lookup"><span data-stu-id="d8024-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="d8024-109">in Dimensione, in caratteri wide, di `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="d8024-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="d8024-110">out Dimensione, in byte, dell'oggetto restituito `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="d8024-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8024-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8024-111">Requirements</span></span>  
 <span data-ttu-id="d8024-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8024-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8024-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d8024-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8024-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8024-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8024-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8024-115">See also</span></span>

- [<span data-ttu-id="d8024-116">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="d8024-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
