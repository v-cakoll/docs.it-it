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
ms.openlocfilehash: 2cb4c79601061ab8473d6d7ca50c4ed2f92b01c4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893433"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>Metodo ICorDebugCode3::GetReturnValueLiveOffset
Per un offset IL specificato, ottiene gli offset nativi in cui deve essere inserito un punto di interruzione in modo che il debugger possa ottenere il valore restituito da una funzione.  
  
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
 Numero di byte disponibili per l'archiviazione `pOffsets`.  
  
 `pFetched`  
 Puntatore al numero di offset effettivamente restituiti. In genere, il valore è 1, ma una singola istruzione IL può eseguire il `CALL` mapping a più istruzioni di assembly.  
  
 `pOffsets`  
 Matrice di offset nativi. In genere `pOffsets` , contiene un singolo offset, sebbene sia possibile eseguire il mapping di una singola istruzione il `CALL` a più istruzioni di assembly.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo viene usato insieme al metodo [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) per ottenere il valore restituito di un metodo che restituisce un tipo di riferimento. Il passaggio di un offset IL a un sito di chiamata di funzione a questo metodo restituisce uno o più offset nativi. Il debugger può quindi impostare punti di interruzione su questi offset nativi nella funzione. Quando il debugger raggiunge uno dei punti di interruzione, è possibile passare lo stesso offset IL passato a questo metodo al metodo [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) per ottenere il valore restituito. Il debugger dovrebbe quindi cancellare tutti i punti di interruzione impostati.  
  
> [!WARNING]
> I `ICorDebugCode3::GetReturnValueLiveOffset` metodi e [ICorDebugILFrame3:: GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) consentono di ottenere informazioni sul valore restituito solo per i tipi di riferimento. Il recupero delle informazioni sul valore restituito dai tipi di valore (ovvero tutti i tipi che derivano da <xref:System.ValueType>) non è supportato.  
  
 La funzione restituisce i `HRESULT` valori mostrati nella tabella seguente.  
  
|Valore della proprietà `HRESULT`|Description|  
|---------------------|-----------------|  
|`S_OK`|Operazione completata.|  
|`CORDBG_E_INVALID_OPCODE`|Il sito di offset IL specificato non è un'istruzione di chiamata o la funzione `void`restituisce.|  
|`CORDBG_E_UNSUPPORTED`|L'offset IL specificato è una chiamata corretta, ma il tipo restituito non è supportato per ottenere un valore restituito.|  
  
 Il `ICorDebugCode3::GetReturnValueLiveOffset` metodo è disponibile solo nei sistemi basati su x86 e amd64.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [Interfaccia ICorDebugCode3](icordebugcode3-interface.md)
