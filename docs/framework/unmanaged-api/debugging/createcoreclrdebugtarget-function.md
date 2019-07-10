---
title: Funzione CreateCoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbcf6c842e7eee55609a9ea2a25cda4360f8dc95
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739297"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="adfa3-102">Funzione CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="adfa3-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="adfa3-103">Crea una connessione a un proxy debugger che è in esecuzione in un computer remoto e restituisce un [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) oggetto che può essere utilizzato per eseguire query sui processi in esecuzione e dei runtime caricati sul computer remoto.</span><span class="sxs-lookup"><span data-stu-id="adfa3-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adfa3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="adfa3-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adfa3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="adfa3-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="adfa3-106">[in] Indirizzo IPv4 di un computer di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="adfa3-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="adfa3-107">[out] Puntatore a un puntatore a un [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) oggetto che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="adfa3-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adfa3-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="adfa3-108">Return Value</span></span>  
 <span data-ttu-id="adfa3-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="adfa3-109">S_OK</span></span>  
 <span data-ttu-id="adfa3-110">Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.</span><span class="sxs-lookup"><span data-stu-id="adfa3-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="adfa3-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="adfa3-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="adfa3-112">Non è possibile allocare memoria sufficiente per `ppTarget`.</span><span class="sxs-lookup"><span data-stu-id="adfa3-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="adfa3-113">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="adfa3-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="adfa3-114">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="adfa3-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adfa3-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="adfa3-115">Requirements</span></span>  
 <span data-ttu-id="adfa3-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adfa3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adfa3-117">**Intestazione:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="adfa3-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="adfa3-118">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="adfa3-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="adfa3-119">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="adfa3-119">**.NET Framework Versions:** 3.5 SP1</span></span>
