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
ms.openlocfilehash: 340d2de09562ea9b767203a7fa839cdc6b729b3b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860899"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="66991-102">Funzione CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="66991-102">CreateCordbObject Function</span></span>
<span data-ttu-id="66991-103">Crea un'interfaccia del debugger ([ICorDebug](icordebug-interface.md)) che fornisce la funzionalità per creare un'istanza di una sessione di debug gestita in un processo remoto.</span><span class="sxs-lookup"><span data-stu-id="66991-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66991-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66991-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66991-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="66991-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="66991-106">[in] Versione del debugger del processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="66991-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="66991-107">Questo parametro deve essere CorDebugVersion_2_0 per il debug remoto.</span><span class="sxs-lookup"><span data-stu-id="66991-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="66991-108">out Puntatore a un puntatore a un oggetto di cui verrà eseguito il cast a un'interfaccia [ICorDebug](icordebug-interface.md) e restituito.</span><span class="sxs-lookup"><span data-stu-id="66991-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66991-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="66991-109">Return Value</span></span>  
 <span data-ttu-id="66991-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="66991-110">S_OK</span></span>  
 <span data-ttu-id="66991-111">Il numero di CLR nel processo è stato determinato correttamente e le matrici di percorsi e di handle corrispondenti sono state riempite correttamente.</span><span class="sxs-lookup"><span data-stu-id="66991-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="66991-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="66991-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="66991-113">`ppCordb` è null o `iDebuggerVersion` non è CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="66991-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="66991-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="66991-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="66991-115">Non è possibile allocare memoria sufficiente per `ppCordb`.</span><span class="sxs-lookup"><span data-stu-id="66991-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="66991-116">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="66991-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="66991-117">Altri errori.</span><span class="sxs-lookup"><span data-stu-id="66991-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66991-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="66991-118">Remarks</span></span>  
 <span data-ttu-id="66991-119">L'interfaccia [ICorDebug](icordebug-interface.md) restituita in `ppCordb` è l'interfaccia di debug di primo livello per tutti i servizi di debug gestito.</span><span class="sxs-lookup"><span data-stu-id="66991-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66991-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="66991-120">Requirements</span></span>  
 <span data-ttu-id="66991-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66991-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66991-122">**Intestazione:** CoreClrRemoteDebuggingInterfaces. h</span><span class="sxs-lookup"><span data-stu-id="66991-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="66991-123">**Libreria:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="66991-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="66991-124">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="66991-124">**.NET Framework Versions:** 3.5 SP1</span></span>
