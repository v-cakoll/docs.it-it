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
ms.openlocfilehash: 48ce5381c745669b813f5b28d801add7daba7825
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965839"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="2b2db-102">Funzione CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="2b2db-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="2b2db-103">Crea una connessione a un proxy debugger che è in esecuzione in un computer remoto e restituisce un [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) oggetto che può essere utilizzato per eseguire query sui processi in esecuzione e dei runtime caricati sul computer remoto.</span><span class="sxs-lookup"><span data-stu-id="2b2db-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b2db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b2db-104">Syntax</span></span>  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b2db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b2db-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="2b2db-106">[in] Indirizzo IPv4 di un computer di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="2b2db-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="2b2db-107">[out] Puntatore a un puntatore a un [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) oggetto che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="2b2db-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b2db-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2b2db-108">Return Value</span></span>  
 <span data-ttu-id="2b2db-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b2db-109">S_OK</span></span>  
 <span data-ttu-id="2b2db-110">Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.</span><span class="sxs-lookup"><span data-stu-id="2b2db-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="2b2db-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2b2db-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2b2db-112">Non è possibile allocare memoria sufficiente per `ppTarget`.</span><span class="sxs-lookup"><span data-stu-id="2b2db-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="2b2db-113">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="2b2db-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2b2db-114">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="2b2db-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b2db-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b2db-115">Requirements</span></span>  
 <span data-ttu-id="2b2db-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b2db-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b2db-117">**Intestazione:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="2b2db-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2b2db-118">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="2b2db-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2b2db-119">**Versioni di .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2b2db-119">**.NET Framework Versions:** 3.5 SP1</span></span>
