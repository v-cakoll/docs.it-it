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
ms.openlocfilehash: a01e2fcc7dc00d3a57272abb04ebcecc6d5f74a6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467072"
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
 Un puntatore all'indirizzo di un oggetto di interfaccia "ICorDebugValue" che fornisce informazioni sul valore restituito di una chiamata di funzione.  
  
## <a name="remarks"></a>Note  
 Questo metodo viene utilizzato con il [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) metodo per ottenere il valore restituito di un metodo. È particolarmente utile nel caso di metodi i cui valori restituiti vengono ignorati, come illustrato di seguito due esempi di codice. Il primo esempio viene chiamato il <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> (metodo), ma ignora valore restituito del metodo.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Nel secondo esempio viene illustrato un problema molto più comune di debug. Poiché un metodo viene usato come argomento in una chiamata al metodo, il relativo valore restituito è accessibile solo quando il debugger eseguirà tramite il metodo chiamato. In molti casi, in particolare quando il metodo chiamato è definito in una libreria esterna, che non è possibile.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Se si passa il [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) metodo un offset IL a un sito di chiamata di funzione, restituisce uno o più offset nativi. Il debugger può quindi impostare i punti di interruzione su questi offset nativi nella funzione. Quando il debugger raggiunge uno dei punti di interruzione, è quindi possibile passare lo stesso offset IL passato al metodo per ottenere il valore restituito. Il debugger dovrà quindi cancellare tutti i punti di interruzione impostato.  
  
> [!WARNING]
>  Il [metodo ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) e `ICorDebugILFrame3::GetReturnValueForILOffset` metodi consentono di ottenere informazioni sul valore restituito per solo i tipi di riferimento. Recupero di informazioni sul valore restituito da tipi di valore (ovvero, tutti i tipi che derivano da <xref:System.ValueType>) non è supportato.  
  
 L'offset IL specificato dal `ILOffset` il parametro deve essere in un sito di chiamata di funzione e l'oggetto del debug deve essere arrestato a un punto di interruzione impostato in corrispondenza dell'offset nativo restituito dal [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) (metodo) per lo stesso offset IL. Se l'oggetto del debug non è stato arrestato in corrispondenza della posizione corretta per l'offset IL specificato, l'API avrà esito negativo.  
  
 Se la chiamata di funzione non restituisce alcun valore, l'API avrà esito negativo.  
  
 Il `ICorDebugILFrame3::GetReturnValueForILOffset` metodo è disponibile solo in basati su x86 e AMD64 sistemi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Metodo GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [Interfaccia ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
