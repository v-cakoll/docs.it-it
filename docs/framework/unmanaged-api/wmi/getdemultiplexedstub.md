---
title: Funzione GetDemultiplexedStub (riferimenti alle API non gestite)
description: La funzione GetDemultiplexedStub crea un sink di server d'avanzamento oggetto per consentire a un client di ricevere chiamate asincrone dalla gestione di Windows.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 9cc028b3300b43f8a0fb3e29f8b5ac6e1817b8c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127462"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="c1a3f-103">GetDemultiplexedStub (funzione)</span><span class="sxs-lookup"><span data-stu-id="c1a3f-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="c1a3f-104">Crea un sink di inoltro oggetti per consentire a un client di ricevere chiamate asincrone da Gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="c1a3f-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c1a3f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1a3f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="c1a3f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1a3f-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="c1a3f-107">in Puntatore all'implementazione in-process del client di [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="c1a3f-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="c1a3f-108">in Flag che indica se l'evento è locale (`true`); in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c1a3f-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="c1a3f-109">out Sink di server d'avanzamento oggetto per consentire a un client di ricevere chiamate asincrone dalla gestione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c1a3f-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="c1a3f-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c1a3f-110">Return value</span></span>

<span data-ttu-id="c1a3f-111">Se la funzione ha esito positivo, il valore restituito è `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="c1a3f-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="c1a3f-112">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="c1a3f-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="c1a3f-113">Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="c1a3f-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="c1a3f-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1a3f-114">Requirements</span></span>  
 <span data-ttu-id="c1a3f-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1a3f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1a3f-116">**Intestazione:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="c1a3f-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c1a3f-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c1a3f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a3f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1a3f-118">See also</span></span>

- [<span data-ttu-id="c1a3f-119">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c1a3f-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
