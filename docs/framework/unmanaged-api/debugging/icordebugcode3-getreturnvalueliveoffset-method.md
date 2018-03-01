---
title: Metodo ICorDebugCode3::GetReturnValueLiveOffset
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d10d298a031e7146eaf6cf7988538e6f7020136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>Metodo ICorDebugCode3::GetReturnValueLiveOffset
Per un offset IL specificato, ottiene gli offset nativi in un punto di interruzione deve essere posizionato in modo che il debugger è possibile ottenere il valore restituito da una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ILoffset`  
 Offset IL. Deve essere un sito di chiamata di funzione o la chiamata di funzione non riuscirà.  
  
 `bufferSize`  
 Il numero di byte disponibili per archiviare `pOffsets`.  
  
 `pFetched`  
 Puntatore al numero di offset effettivamente restituiti. In genere, il relativo valore è 1, ma è possibile eseguire il mapping di una singola istruzione IL multiplo `CALL` le istruzioni di assembly.  
  
 `pOffsets`  
 Matrice di offset nativi. In genere, `pOffsets` contiene solo un offset, anche se è possibile eseguire il mapping di una singola istruzione di linguaggio intermedio con mapping più in più `CALL` le istruzioni di assembly.  
  
## <a name="remarks"></a>Note  
 Questo metodo viene utilizzato insieme al [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodo per ottenere il valore restituito di un metodo che restituisce un tipo di riferimento. Il passaggio di un offset a un sito di chiamata di funzione per questo metodo IL restituisce uno o più offset nativi. Il debugger può quindi impostare i punti di interruzione in questi offset nativi nella funzione. Quando il debugger raggiunge uno dei punti di interruzione, è quindi possibile passare lo stesso offset IL che è stato passato a questo metodo per il [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodo per ottenere il valore restituito. Il debugger deve quindi deselezionare tutti i punti di interruzione è impostato.  
  
> [!WARNING]
>  Il `ICorDebugCode3::GetReturnValueLiveOffset` e [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) metodi consentono di ottenere informazioni sul valore restituito per solo i tipi di riferimento. Recupero delle informazioni di valore restituito da tipi di valore (vale a dire tutti i tipi che derivano da <xref:System.ValueType>) non è supportata.  
  
 La funzione restituisce il `HRESULT` sui valori indicati nella tabella seguente.  
  
|Valore di `HRESULT`|Descrizione|  
|---------------------|-----------------|  
|`S_OK`|Operazione completata.|  
|`CORDBG_E_INVALID_OPCODE`|Il sito di offset IL specificato non è un'istruzione di chiamata o la funzione restituisce `void`.|  
|`CORDBG_E_UNSUPPORTED`|L'offset IL specificato è una chiamata corretta, ma il tipo restituito non è supportato per il recupero di un valore restituito.|  
  
 Il `ICorDebugCode3::GetReturnValueLiveOffset` metodo è disponibile solo nel server basato su x86 e sistemi AMD64.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [Interfaccia ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
