---
title: Metodo ICorDebugCode3::GetReturnValueLiveOffset
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03ee275336d3ae71f63d82add694fe1308efbe8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750058"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>Metodo ICorDebugCode3::GetReturnValueLiveOffset
Per un offset IL specificato, ottiene l'offset nativi in cui un punto di interruzione deve essere inserito in modo che il debugger può ottenere il valore restituito da una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ILoffset`  
 Offset IL. Deve essere un sito di chiamata di funzione o la chiamata di funzione avrà esito negativo.  
  
 `bufferSize`  
 Il numero di byte disponibili per l'archiviazione `pOffsets`.  
  
 `pFetched`  
 Puntatore al numero di offset effettivamente restituiti. In genere, il valore è 1, ma una singola istruzione IL può eseguire il mapping a più `CALL` le istruzioni di assembly.  
  
 `pOffsets`  
 Matrice di offset nativi. In genere `pOffsets` contiene un singolo offset, sebbene una singola istruzione IL può eseguire il mapping a più `CALL` le istruzioni di assembly.  
  
## <a name="remarks"></a>Note  
 Questo metodo viene utilizzato con il [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodo per ottenere il valore restituito di un metodo che restituisce un tipo di riferimento. Il passaggio di un offset IL a un sito di chiamata di funzione a questo metodo restituisce uno o più offset nativi. Il debugger può quindi impostare i punti di interruzione su questi offset nativi nella funzione. Quando il debugger raggiunge uno dei punti di interruzione, è possibile passare lo stesso offset IL passato al metodo per la [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodo per ottenere il valore restituito. Il debugger dovrà quindi cancellare tutti i punti di interruzione impostato.  
  
> [!WARNING]
>  Il `ICorDebugCode3::GetReturnValueLiveOffset` e [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodi consentono di ottenere informazioni sul valore restituito per solo i tipi di riferimento. Recupero di informazioni sul valore restituito da tipi di valore (ovvero, tutti i tipi che derivano da <xref:System.ValueType>) non è supportato.  
  
 La funzione restituisce il `HRESULT` sui valori indicati nella tabella seguente.  
  
|Valore di`HRESULT` |Descrizione|  
|---------------------|-----------------|  
|`S_OK`|Operazione completata.|  
|`CORDBG_E_INVALID_OPCODE`|Il sito di offset IL specificato non è un'istruzione di chiamata o la funzione restituisce `void`.|  
|`CORDBG_E_UNSUPPORTED`|L'offset IL specificato è una chiamata corretta, ma il tipo restituito non è supportato per ottenere un valore restituito.|  
  
 Il `ICorDebugCode3::GetReturnValueLiveOffset` metodo è disponibile solo in basati su x86 e AMD64 sistemi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)
- [Interfaccia ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
