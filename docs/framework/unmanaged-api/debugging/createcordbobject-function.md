---
title: Funzione CreateCordbObject
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: 2716adcc8c79c8003202561ea2011c2469a6bc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179226"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="4f87a-102">Funzione CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="4f87a-102">CreateCordbObject Function</span></span>
<span data-ttu-id="4f87a-103">Crea un'interfaccia del debugger ([ICorDebug](icordebug-interface.md)) che fornisce la funzionalità per la creazione di un'istanza di una sessione di debug gestito in un processo remoto.</span><span class="sxs-lookup"><span data-stu-id="4f87a-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f87a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f87a-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f87a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f87a-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="4f87a-106">[in] Versione del debugger del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4f87a-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="4f87a-107">Questo parametro deve essere CorDebugVersion_2_0 per il debug remoto.</span><span class="sxs-lookup"><span data-stu-id="4f87a-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="4f87a-108">[fuori] Puntatore a un puntatore a un oggetto di cui verrà eseguito il cast a un [ICorDebug](icordebug-interface.md) interfaccia e restituito.</span><span class="sxs-lookup"><span data-stu-id="4f87a-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f87a-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4f87a-109">Return Value</span></span>  
 <span data-ttu-id="4f87a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f87a-110">S_OK</span></span>  
 <span data-ttu-id="4f87a-111">Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.</span><span class="sxs-lookup"><span data-stu-id="4f87a-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="4f87a-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4f87a-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="4f87a-113">`ppCordb` è null o `iDebuggerVersion` non è CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="4f87a-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="4f87a-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4f87a-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="4f87a-115">Non è possibile allocare memoria sufficiente per `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="4f87a-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="4f87a-116">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="4f87a-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="4f87a-117">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="4f87a-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f87a-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4f87a-118">Remarks</span></span>  
 <span data-ttu-id="4f87a-119">Il [ICorDebug](icordebug-interface.md) interfaccia che `ppCordb` viene restituita in è l'interfaccia di debug di primo livello per tutti i servizi di debug gestito.</span><span class="sxs-lookup"><span data-stu-id="4f87a-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f87a-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f87a-120">Requirements</span></span>  
 <span data-ttu-id="4f87a-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f87a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f87a-122">**Intestazione:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="4f87a-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="4f87a-123">**Libreria:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="4f87a-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="4f87a-124">Versioni di **.NET Framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="4f87a-124">**.NET Framework Versions:** 3.5 SP1</span></span>
