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
ms.openlocfilehash: 1d190c5b558c7c523be09267e59eab7c5611563a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793862"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="2defe-102">Funzione CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="2defe-102">CreateCordbObject Function</span></span>
<span data-ttu-id="2defe-103">Crea un'interfaccia del debugger ([ICorDebug](icordebug-interface.md)) che fornisce la funzionalità per creare un'istanza di una sessione di debug gestita in un processo remoto.</span><span class="sxs-lookup"><span data-stu-id="2defe-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2defe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2defe-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2defe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2defe-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="2defe-106">[in] Versione del debugger del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2defe-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="2defe-107">Questo parametro deve essere CorDebugVersion_2_0 per il debug remoto.</span><span class="sxs-lookup"><span data-stu-id="2defe-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="2defe-108">out Puntatore a un puntatore a un oggetto di cui verrà eseguito il cast a un'interfaccia [ICorDebug](icordebug-interface.md) e restituito.</span><span class="sxs-lookup"><span data-stu-id="2defe-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2defe-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2defe-109">Return Value</span></span>  
 <span data-ttu-id="2defe-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2defe-110">S_OK</span></span>  
 <span data-ttu-id="2defe-111">Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.</span><span class="sxs-lookup"><span data-stu-id="2defe-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="2defe-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2defe-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="2defe-113">`ppCordb` è null o `iDebuggerVersion` non è CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="2defe-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="2defe-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2defe-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="2defe-115">Non è possibile allocare memoria sufficiente per `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="2defe-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="2defe-116">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="2defe-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="2defe-117">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="2defe-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2defe-118">Note</span><span class="sxs-lookup"><span data-stu-id="2defe-118">Remarks</span></span>  
 <span data-ttu-id="2defe-119">L'interfaccia [ICorDebug](icordebug-interface.md) restituita in `ppCordb` è l'interfaccia di debug di primo livello per tutti i servizi di debug gestito.</span><span class="sxs-lookup"><span data-stu-id="2defe-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2defe-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2defe-120">Requirements</span></span>  
 <span data-ttu-id="2defe-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2defe-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2defe-122">**Intestazione:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="2defe-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="2defe-123">**Libreria:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="2defe-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="2defe-124">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="2defe-124">**.NET Framework Versions:** 3.5 SP1</span></span>
