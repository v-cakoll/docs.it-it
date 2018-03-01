---
title: Metodo ICorDebugILFrame3::GetReturnValueForILOffset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c58319de99bdd8d7cce0ea55ccb3140a31a39bd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parametri  
 `ILOffset`  
 Offset IL. Vedere la sezione Osservazioni.  
  
 `ppReturnValue`  
 Un puntatore all'indirizzo di un oggetto di interfaccia "ICorDebugValue" che fornisce informazioni sul valore restituito di una chiamata di funzione.  
  
## <a name="remarks"></a>Note  
 Questo metodo viene utilizzato insieme al [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) metodo per ottenere il valore restituito di un metodo. È particolarmente utile nel caso di metodi i cui valori restituiti vengono ignorati, come illustrato negli esempi di codice seguente. Nell'esempio viene chiamato prima di <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> (metodo), ma ignora valore restituito del metodo.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 Nel secondo esempio viene illustrato un problema più comune di debug. Un metodo viene utilizzato come argomento in una chiamata al metodo, il relativo valore restituito è accessibile solo quando il debugger eseguirà tramite il metodo chiamato. In molti casi, in particolare quando il metodo chiamato è definito in una libreria esterna, che non è possibile.  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 Se si passa il [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) un offset a un sito di chiamata di funzione IL, restituisce uno o più offset nativi. Il debugger può quindi impostare i punti di interruzione in questi offset nativi nella funzione. Quando il debugger raggiunge uno dei punti di interruzione, è quindi possibile passare lo stesso offset di linguaggio intermedio che è stato passato a questo metodo per ottenere il valore restituito. Il debugger deve quindi deselezionare tutti i punti di interruzione è impostato.  
  
> [!WARNING]
>  Il [metodo icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) e `ICorDebugILFrame3::GetReturnValueForILOffset` metodi consentono di ottenere informazioni sul valore restituito per solo i tipi di riferimento. Recupero delle informazioni di valore restituito da tipi di valore (vale a dire tutti i tipi che derivano da <xref:System.ValueType>) non è supportata.  
  
 Offset IL specificato per il `ILOffset` parametro deve essere in un sito di chiamata di funzione e l'oggetto del debug deve essere interrotta in un punto di interruzione impostato in corrispondenza dell'offset nativo restituito dal [icordebugcode3:: Getreturnvalueliveoffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) (metodo) per lo stesso offset IL. Se l'oggetto del debug non è stato arrestato in corrispondenza della posizione corretta per l'offset IL specificato, l'API avrà esito negativo.  
  
 Se la chiamata di funzione non restituisce alcun valore, l'API avrà esito negativo.  
  
 Il `ICorDebugILFrame3::GetReturnValueForILOffset` metodo è disponibile solo nel server basato su x86 e sistemi AMD64.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)  
 [Interfaccia ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
