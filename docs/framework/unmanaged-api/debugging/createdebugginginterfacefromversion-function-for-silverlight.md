---
title: Funzione di Silverlight CreateDebuggingInterfaceFromVersion
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
ms.openlocfilehash: c83bdcca4fab75b4ae94500ceb785b6000cd802a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860873"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="757a2-102">Funzione di Silverlight CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="757a2-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="757a2-103">Accetta una stringa di versione Common Language Runtime (CLR) restituita dalla [funzione CreateVersionStringFromModule](createversionstringfrommodule-function.md)e restituisce un'interfaccia del debugger corrispondente (in genere, [ICorDebug](icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="757a2-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="757a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="757a2-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="757a2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="757a2-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="757a2-106">in Stringa di versione di CLR nell'oggetto del debug di destinazione, restituito dalla [funzione CreateVersionStringFromModule](createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="757a2-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="757a2-107">[out] Puntatore a un puntatore a un oggetto COM (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="757a2-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="757a2-108">Viene eseguito il cast di questo oggetto a un oggetto [ICorDebug](icordebug-interface.md) prima che venga restituito.</span><span class="sxs-lookup"><span data-stu-id="757a2-108">This object will be cast to an [ICorDebug](icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="757a2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="757a2-109">Return Value</span></span>  
 <span data-ttu-id="757a2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="757a2-110">S_OK</span></span>  
 <span data-ttu-id="757a2-111">`ppCordb`fa riferimento a un oggetto valido che implementa l'interfaccia dell' [interfaccia ICorDebug](icordebug-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="757a2-111">`ppCordb` references a valid object that implements the [ICorDebug interface](icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="757a2-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="757a2-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="757a2-113">`szDebuggeeVersion` o `ppCordb` è null.</span><span class="sxs-lookup"><span data-stu-id="757a2-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="757a2-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="757a2-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="757a2-115">Impossibile trovare un componente necessario per il debug CLR.</span><span class="sxs-lookup"><span data-stu-id="757a2-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="757a2-116">Ciò significa che non è stato possibile trovare mscordaccore.dll o mscordbi.dll nella stessa directory del file CoreCLR.dll di destinazione.</span><span class="sxs-lookup"><span data-stu-id="757a2-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="757a2-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="757a2-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="757a2-118">Significa che la versione di mscordaccore.dll o mscordbi.dll non corrisponde a quella del file CoreCLR.dll di destinazione.</span><span class="sxs-lookup"><span data-stu-id="757a2-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="757a2-119">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="757a2-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="757a2-120">Impossibile restituire un' [interfaccia ICorDebug](icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="757a2-120">Unable to return an [ICorDebug interface](icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="757a2-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="757a2-121">Remarks</span></span>  
 <span data-ttu-id="757a2-122">L'interfaccia restituita fornisce funzionalità per connettersi a un CLR nel processo di destinazione ed eseguire il debug del codice gestito eseguito da CLR.</span><span class="sxs-lookup"><span data-stu-id="757a2-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="757a2-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="757a2-123">Requirements</span></span>  
 <span data-ttu-id="757a2-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="757a2-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="757a2-125">**Intestazione:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="757a2-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="757a2-126">**Libreria:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="757a2-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="757a2-127">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="757a2-127">**.NET Framework Versions:** 3.5 SP1</span></span>
