---
title: Metodo ICLRMetaHost::ExitProcess
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 83cbfa097541681305ff285f21c2b6c9c6391ef8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703755"
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="4e442-102">Metodo ICLRMetaHost::ExitProcess</span><span class="sxs-lookup"><span data-stu-id="4e442-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="4e442-103">Tenta di arrestare correttamente tutti i runtime caricati, quindi termina il processo.</span><span class="sxs-lookup"><span data-stu-id="4e442-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="4e442-104">Sostituisce la funzione [CorExitProcess](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="4e442-104">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e442-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e442-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e442-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e442-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="4e442-107">in Codice di uscita del processo.</span><span class="sxs-lookup"><span data-stu-id="4e442-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e442-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4e442-108">Return Value</span></span>  
 <span data-ttu-id="4e442-109">Questo metodo non restituisce mai, quindi il valore restituito non è definito.</span><span class="sxs-lookup"><span data-stu-id="4e442-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e442-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4e442-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e442-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e442-111">Requirements</span></span>  
 <span data-ttu-id="4e442-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e442-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e442-113">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="4e442-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4e442-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e442-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e442-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e442-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e442-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e442-116">See also</span></span>

- [<span data-ttu-id="4e442-117">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="4e442-117">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="4e442-118">Hosting</span><span class="sxs-lookup"><span data-stu-id="4e442-118">Hosting</span></span>](index.md)
