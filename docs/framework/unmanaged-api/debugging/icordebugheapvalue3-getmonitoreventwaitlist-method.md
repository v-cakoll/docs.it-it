---
title: Metodo ICorDebugHeapValue3::GetMonitorEventWaitList
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27815cf8cb7fdcd1c01f26391c317d52bbb388ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628513"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>Metodo ICorDebugHeapValue3::GetMonitorEventWaitList
Fornisce un elenco ordinato di thread che vengono messe in coda sull'evento associato a un blocco di monitoraggio.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppThreadEnum`  
 [out] L'enumeratore ICorDebugThreadEnum che fornisce l'elenco ordinato di thread.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|The list is not empty.|  
|S_FALSE|L'elenco è vuoto.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Il primo thread nell'elenco è il primo thread che viene rilasciato per la chiamata successiva a <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>. Il thread successivo nell'elenco è ha rilasciato la seguente chiamata e così via.  
  
 Se l'elenco non è vuoto, questo metodo restituisce S_OK. Se l'elenco è vuoto, il metodo restituisce S_FALSE. In questo caso, l'enumerazione è ancora valido, anche se è vuota.  
  
 In entrambi i casi, l'interfaccia di enumerazione è utilizzabile solo per la durata dello stato di sincronizzazione corrente. Tuttavia, le interfacce del thread erogate da quest'ultimo sono valide fino alla chiusura del thread.  
  
 Se `ppThreadEnum` non è un puntatore valido, il risultato è indefinito.  
  
 Se si verifica un errore in modo che non può essere determinato che, se presente, i thread sono in attesa per il monitoraggio, il metodo restituisce un HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
