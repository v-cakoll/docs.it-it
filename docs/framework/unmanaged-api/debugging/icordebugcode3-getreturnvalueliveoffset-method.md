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
ms.openlocfilehash: 34d543dd76de05bdf55d8187cf192455d1387a9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178949"
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
 Numero di byte disponibili `pOffsets`per l'archivio.  
  
 `pFetched`  
 Puntatore al numero di offset effettivamente restituiti. In genere, il valore è 1, ma `CALL` una singola istruzione IL può eseguire il mapping a più istruzioni di assembly.  
  
 `pOffsets`  
 Matrice di offset nativi. In `pOffsets` genere, contiene un singolo offset, anche se una `CALL` singola istruzione IL può eseguire il mapping a più istruzioni di assemblaggio.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo viene utilizzato insieme al [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) metodo per ottenere il valore restituito di un metodo che restituisce un tipo di riferimento. Il passaggio di un offset IL a un sito di chiamata di funzione a questo metodo restituisce uno o più offset nativi. Il debugger può quindi impostare punti di interruzione su questi offset nativi nella funzione. Quando il debugger raggiunge uno dei punti di interruzione, è quindi possibile passare lo stesso offset IL passato a questo metodo al metodo [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) per ottenere il valore restituito. Il debugger deve quindi cancellare tutti i punti di interruzione impostati.  
  
> [!WARNING]
> I `ICorDebugCode3::GetReturnValueLiveOffset` metodi e [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) consentono di ottenere informazioni sui valori restituiti solo per i tipi di riferimento. Il recupero di informazioni sul valore restituito dai tipi <xref:System.ValueType>di valore, ovvero tutti i tipi che derivano da , non è supportato.  
  
 La funzione `HRESULT` restituisce i valori illustrati nella tabella seguente.  
  
|Valore della proprietà `HRESULT`|Descrizione|  
|---------------------|-----------------|  
|`S_OK`|Esito positivo.|  
|`CORDBG_E_INVALID_OPCODE`|Il sito di offset IL specificato non è `void`un'istruzione di chiamata o la funzione restituisce .|  
|`CORDBG_E_UNSUPPORTED`|L'offset IL specificato è una chiamata corretta, ma il tipo restituito non è supportato per ottenere un valore restituito.|  
  
 Il `ICorDebugCode3::GetReturnValueLiveOffset` metodo è disponibile solo su sistemi x86 e AMD64.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [Interfaccia ICorDebugCode3](icordebugcode3-interface.md)
