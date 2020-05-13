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
ms.openlocfilehash: 923e9b0821788143fff59eafe10d1802583df7a6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210423"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a>Metodo ICorDebugHeapValue3::GetMonitorEventWaitList
Fornisce un elenco ordinato di thread accodati per l'evento associato a un blocco di monitoraggio.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppThreadEnum`  
 out Enumeratore ICorDebugThreadEnum che fornisce l'elenco ordinato di thread.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|The list is not empty.|  
|S_FALSE|L'elenco è vuoto.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Osservazioni  
 Il primo thread nell'elenco è il primo thread rilasciato dalla chiamata successiva a <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType> . Il thread successivo nell'elenco viene rilasciato nella chiamata seguente e così via.  
  
 Se l'elenco non è vuoto, questo metodo restituisce S_OK. Se l'elenco è vuoto, il metodo restituisce S_FALSE; in questo caso, l'enumerazione è ancora valida, anche se è vuota.  
  
 In entrambi i casi, l'interfaccia di enumerazione è utilizzabile solo per la durata dello stato sincronizzato corrente. Tuttavia, le interfacce del thread da esso disposte sono valide fino alla chiusura del thread.  
  
 Se `ppThreadEnum` non è un puntatore valido, il risultato è indefinito.  
  
 Se si verifica un errore in modo che non possa essere determinato quale, se presente, i thread sono in attesa del monitoraggio, il metodo restituisce un valore HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
