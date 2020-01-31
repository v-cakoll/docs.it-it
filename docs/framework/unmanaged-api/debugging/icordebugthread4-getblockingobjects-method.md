---
title: Metodo ICorDebugThread4::GetBlockingObjects
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: 39833b689f28437b4241d9cb15fb4a92b2f9bcc3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791379"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="fc624-102">Metodo ICorDebugThread4::GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="fc624-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="fc624-103">Fornisce un'enumerazione ordinata di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) che forniscono informazioni di blocco del thread.</span><span class="sxs-lookup"><span data-stu-id="fc624-103">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc624-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc624-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc624-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc624-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="fc624-106">out Puntatore a un'enumerazione ordinata di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="fc624-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc624-107">Note</span><span class="sxs-lookup"><span data-stu-id="fc624-107">Remarks</span></span>  
 <span data-ttu-id="fc624-108">Il primo elemento nell'enumerazione restituita corrisponde alla prima struttura che blocca il thread.</span><span class="sxs-lookup"><span data-stu-id="fc624-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="fc624-109">Il secondo elemento corrisponde a un elemento di blocco rilevato durante l'esecuzione di una chiamata di procedura asincrona (APC) quando viene bloccato sul primo e così via.</span><span class="sxs-lookup"><span data-stu-id="fc624-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="fc624-110">L'enumerazione è valida solo per la durata dello stato sincronizzato corrente.</span><span class="sxs-lookup"><span data-stu-id="fc624-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="fc624-111">Questo metodo deve essere chiamato quando l'oggetto del debug è in stato SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="fc624-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="fc624-112">Se `ppBlockingObjectEnum` non è un puntatore valido, il risultato è indefinito.</span><span class="sxs-lookup"><span data-stu-id="fc624-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="fc624-113">Se un thread è bloccato e non è possibile determinare l'errore, il metodo restituisce un valore HRESULT che indica un errore. in caso contrario, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="fc624-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc624-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="fc624-114">Requirements</span></span>  
 <span data-ttu-id="fc624-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc624-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc624-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc624-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc624-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc624-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc624-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc624-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc624-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc624-119">See also</span></span>

- [<span data-ttu-id="fc624-120">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="fc624-120">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="fc624-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fc624-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fc624-122">Debug</span><span class="sxs-lookup"><span data-stu-id="fc624-122">Debugging</span></span>](index.md)
