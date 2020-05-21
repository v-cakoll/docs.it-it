---
title: Metodo ICorRuntimeHost::MapFile
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
ms.openlocfilehash: 3b1a0cd9a1dfba6f33a20416f2a10c967f871a06
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762669"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="e4300-102">Metodo ICorRuntimeHost::MapFile</span><span class="sxs-lookup"><span data-stu-id="e4300-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="e4300-103">Esegue il mapping del file specificato in memoria.</span><span class="sxs-lookup"><span data-stu-id="e4300-103">Maps the specified file into memory.</span></span> <span data-ttu-id="e4300-104">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="e4300-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4300-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4300-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4300-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e4300-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="e4300-107">in Handle del file di cui eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="e4300-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="e4300-108">out Indirizzo di memoria iniziale da cui iniziare il mapping del file.</span><span class="sxs-lookup"><span data-stu-id="e4300-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4300-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4300-109">Requirements</span></span>  
 <span data-ttu-id="e4300-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4300-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4300-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e4300-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4300-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e4300-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4300-113">**Versione .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e4300-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4300-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4300-114">See also</span></span>

- [<span data-ttu-id="e4300-115">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e4300-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
