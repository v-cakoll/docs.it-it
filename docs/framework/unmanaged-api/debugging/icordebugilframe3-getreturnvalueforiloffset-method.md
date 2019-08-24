---
title: Metodo ICorDebugILFrame3::GetReturnValueForILOffset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5832ec095ea0e96327f6a9636193da9c0c8a5dd2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988271"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a>Metodo ICorDebugILFrame3::GetReturnValueForILOffset
Ottiene un oggetto "ICorDebugValue" che incapsula il valore restituito di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ILOffset`  
 Offset IL. Vedere la sezione Osservazioni.  
  
 `ppReturnValue`  
 Puntatore all'indirizzo di un oggetto interfaccia "ICorDebugValue" che fornisce informazioni sul valore restituito di una chiamata di funzione.  
  
## <a name="remarks"></a>Note  
 Questo metodo viene usato insieme al metodo [ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) per ottenere il valore restituito di un metodo. È particolarmente utile nel caso di metodi i cui valori restituiti vengono ignorati, come nei due esempi di codice seguenti. Nel primo esempio viene chiamato <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> il metodo, ma viene ignorato il valore restituito del metodo.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Nel secondo esempio viene illustrato un problema molto più comune nel debug. Poiché un metodo viene usato come argomento in una chiamata al metodo, il relativo valore restituito è accessibile solo quando il debugger passa attraverso il metodo chiamato. In molti casi, in particolare quando il metodo chiamato viene definito in una libreria esterna, non è possibile.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Se si passa il metodo [ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) un offset il a un sito di chiamata di funzione, viene restituito uno o più offset nativi. Il debugger può quindi impostare punti di interruzione su questi offset nativi nella funzione. Quando il debugger raggiunge uno dei punti di interruzione, è possibile passare lo stesso offset IL passato a questo metodo per ottenere il valore restituito. Il debugger dovrebbe quindi cancellare tutti i punti di interruzione impostati.  
  
> [!WARNING]
> Il [Metodo ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) e `ICorDebugILFrame3::GetReturnValueForILOffset` i metodi consentono di ottenere informazioni sul valore restituito solo per i tipi di riferimento. Il recupero delle informazioni sul valore restituito dai tipi di valore (ovvero tutti i tipi che derivano da <xref:System.ValueType>) non è supportato.  
  
 L'offset il specificato dal `ILOffset` parametro deve trovarsi in un sito di chiamata di funzione e l'oggetto del debug deve essere interrotto in corrispondenza di un punto di interruzione impostato in corrispondenza dell'offset nativo restituito dal metodo [ICorDebugCode3:: GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) per lo stesso offset il. Se l'oggetto del debug non viene arrestato nella posizione corretta per l'offset IL specificato, l'API avrà esito negativo.  
  
 Se la chiamata di funzione non restituisce un valore, l'API avrà esito negativo.  
  
 Il `ICorDebugILFrame3::GetReturnValueForILOffset` metodo è disponibile solo nei sistemi basati su x86 e amd64.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [Interfaccia ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
