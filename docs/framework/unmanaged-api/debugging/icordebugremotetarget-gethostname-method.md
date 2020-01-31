---
title: Metodo ICorDebugRemoteTarget::GetHostName
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: f177d441da3bd967750781e487d9fed42bc132f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791940"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="83e62-102">Metodo ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="83e62-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="83e62-103">Restituisce il nome di dominio completo o l'indirizzo IPv4 del computer di destinazione per il debug remoto.</span><span class="sxs-lookup"><span data-stu-id="83e62-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="83e62-104">IPV6 non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="83e62-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e62-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83e62-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="83e62-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="83e62-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="83e62-107">in Dimensione, in caratteri, del buffer `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="83e62-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="83e62-108">Se il parametro è 0 (zero), `szHostName` deve essere Null.</span><span class="sxs-lookup"><span data-stu-id="83e62-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="83e62-109">[out] Numero di caratteri, incluso un terminatore Null, nel nome host o nell'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="83e62-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="83e62-110">Questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="83e62-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="83e62-111">[out] Buffer contenente il nome host o l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="83e62-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83e62-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="83e62-112">Return Value</span></span>  
 <span data-ttu-id="83e62-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="83e62-113">S_OK</span></span>  
 <span data-ttu-id="83e62-114">Il nome host o l'indirizzo IP è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="83e62-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="83e62-115">E_FAIL (o altri codici E_ restituiti)</span><span class="sxs-lookup"><span data-stu-id="83e62-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="83e62-116">Impossibile restituire il nome host o l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="83e62-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83e62-117">Note</span><span class="sxs-lookup"><span data-stu-id="83e62-117">Remarks</span></span>  
 <span data-ttu-id="83e62-118">Questo metodo viene implementato dal writer del debugger.</span><span class="sxs-lookup"><span data-stu-id="83e62-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="83e62-119">Deve seguire il paradigma di chiamata multipla: alla prima chiamata, il chiamante passa null a sia `cchHostName` che `szHostName`e `pcchHostName` restituisce la dimensione del buffer richiesto.</span><span class="sxs-lookup"><span data-stu-id="83e62-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="83e62-120">Nella seconda chiamata, la dimensione che è stata restituita in precedenza viene passata a `cchHostName` e un buffer di dimensioni appropriate viene passato a `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="83e62-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83e62-121">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="83e62-121">Requirements</span></span>  
 <span data-ttu-id="83e62-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83e62-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83e62-123">**Intestazione:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="83e62-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="83e62-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83e62-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83e62-125">**Versioni .NET Framework:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="83e62-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e62-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83e62-126">See also</span></span>

- [<span data-ttu-id="83e62-127">Interfaccia ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="83e62-127">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="83e62-128">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="83e62-128">ICorDebug Interface</span></span>](icordebug-interface.md)
