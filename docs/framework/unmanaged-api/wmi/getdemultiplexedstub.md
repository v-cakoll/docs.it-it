---
title: GetDemultiplexedStub function (Unmanaged API Reference)
description: La funzione GetDemultiplexedStub crea un sink di inoltro oggetto per assistere un client nella ricezione di chiamate asincrone da Gestione Windows.The GetDemultiplexedStub function creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.
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
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174966"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="0b3a9-103">Funzione GetDemultiplexedStub</span><span class="sxs-lookup"><span data-stu-id="0b3a9-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="0b3a9-104">Crea un sink di inoltro oggetti per consentire a un client di ricevere chiamate asincrone da Gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="0b3a9-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0b3a9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b3a9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="0b3a9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b3a9-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="0b3a9-107">[in] Puntatore all'implementazione in-process del client di [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="0b3a9-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="0b3a9-108">[in] Flag che indica se l'evento`true`è locale ( ); in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="0b3a9-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="0b3a9-109">[fuori] Un sink del server di inoltro oggetto per assistere un client nella ricezione di chiamate asincrone da Gestione Windows.</span><span class="sxs-lookup"><span data-stu-id="0b3a9-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="0b3a9-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0b3a9-110">Return value</span></span>

<span data-ttu-id="0b3a9-111">Se la funzione ha esito `S_OK` positivo, il valore restituito è (0).</span><span class="sxs-lookup"><span data-stu-id="0b3a9-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="0b3a9-112">Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="0b3a9-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="0b3a9-113">Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo.To](geterrorinfo.md) get extended error information, call the GetErrorInfo function.</span><span class="sxs-lookup"><span data-stu-id="0b3a9-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b3a9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b3a9-114">Requirements</span></span>  
 <span data-ttu-id="0b3a9-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b3a9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b3a9-116">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0b3a9-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0b3a9-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0b3a9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b3a9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b3a9-118">See also</span></span>

- [<span data-ttu-id="0b3a9-119">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="0b3a9-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
