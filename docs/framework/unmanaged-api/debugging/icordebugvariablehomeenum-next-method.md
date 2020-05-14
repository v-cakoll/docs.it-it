---
title: 'ICorDebugVariableHomeEnum:: Next (metodo)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 980f563d3b11fbfcce48b6d7c05275af520e14f1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396497"
---
# <a name="icordebugvariablehomeenumnext-method"></a>ICorDebugVariableHomeEnum:: Next (metodo)
Ottiene il numero specificato di istanze di [ICorDebugVariableHome](icordebugvariablehome-interface.md) che contengono informazioni sulle variabili e gli argomenti locali in una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `celt`  
 [in] Numero di oggetti da recuperare.  
  
 `homes`  
 Matrice di puntatori, ciascuno dei quali punta a un oggetto [ICorDebugVariableHome](icordebugvariablehome-interface.md) che fornisce informazioni su una variabile locale o un argomento di una funzione.  
  
 `pceltFetched`  
 out Numero di istanze effettivamente restituite negli oggetti.  
  
## <a name="return-value"></a>Valore restituito  
 Il metodo restituisce i valori seguenti.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|Metodo completato correttamente.|  
|`S_FALSE`|Il numero effettivo di istanze recuperate, come riflesso in `pceltFetched` , è inferiore al numero di istanze richieste.|  
  
## <a name="remarks"></a>Commenti  
 Il metodo [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) recupera un massimo di `celt` oggetti a partire dalla posizione corrente dell'enumeratore. Quando il metodo viene restituito, `pceltFetched` contiene il numero effettivo di oggetti recuperati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)
- [Interfaccia ICorDebugVariableHome](icordebugvariablehome-interface.md)
