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
ms.openlocfilehash: a7fed8cb70785f0ccfcadf1e16181db303ac98e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789187"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="9abb1-102">Funzione CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="9abb1-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="9abb1-103">Crea una connessione a un proxy del debugger in esecuzione su un computer remoto e restituisce un oggetto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) che può essere usato per eseguire query sui processi in esecuzione e sui runtime caricati nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="9abb1-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9abb1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9abb1-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9abb1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9abb1-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="9abb1-106">[in] Indirizzo IPv4 di un computer di destinazione remoto.</span><span class="sxs-lookup"><span data-stu-id="9abb1-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="9abb1-107">out Puntatore a un puntatore a un oggetto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="9abb1-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9abb1-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9abb1-108">Return Value</span></span>  
 <span data-ttu-id="9abb1-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="9abb1-109">S_OK</span></span>  
 <span data-ttu-id="9abb1-110">Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.</span><span class="sxs-lookup"><span data-stu-id="9abb1-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="9abb1-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9abb1-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="9abb1-112">Non è possibile allocare memoria sufficiente per `ppTarget`.</span><span class="sxs-lookup"><span data-stu-id="9abb1-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="9abb1-113">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="9abb1-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9abb1-114">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="9abb1-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9abb1-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9abb1-115">Requirements</span></span>  
 <span data-ttu-id="9abb1-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9abb1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9abb1-117">**Intestazione:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="9abb1-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="9abb1-118">**Libreria:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="9abb1-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="9abb1-119">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="9abb1-119">**.NET Framework Versions:** 3.5 SP1</span></span>
