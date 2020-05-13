---
title: Interfaccia ICorDebugReferenceValue
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
ms.openlocfilehash: 6c6ff428e378e973d8846674ffacdcd04b2dbdbc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378340"
---
# <a name="icordebugreferencevalue-interface"></a>Interfaccia ICorDebugReferenceValue
Fornisce metodi che gestiscono un valore che è un riferimento a un oggetto. (Ovvero, questa interfaccia fornisce metodi per la gestione di un puntatore). Questa interfaccia implementa "ICorDebugValue".  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Dereference](icordebugreferencevalue-dereference-method.md)|Ottiene l'oggetto a cui si fa riferimento.|  
|[Metodo DereferenceStrong](icordebugreferencevalue-dereferencestrong-method.md)|Non implementato. Non chiamare questo metodo.|  
|[Metodo GetValue](icordebugreferencevalue-getvalue-method.md)|Ottiene l'indirizzo di memoria corrente dell'oggetto a cui si fa riferimento.|  
|[Metodo IsNull](icordebugreferencevalue-isnull-method.md)|Ottiene un valore che indica se si `ICorDebugReferenceValue` tratta di un valore null, nel qual caso `ICorDebugReferenceValue` non punta a un oggetto.|  
|[Metodo SetValue](icordebugreferencevalue-setvalue-method.md)|Imposta l'indirizzo di memoria corrente. Questo metodo imposta questa impostazione in modo che `ICorDebugReferenceValue` punti a un oggetto.|  
  
## <a name="remarks"></a>Osservazioni  
 Il Common Language Runtime (CLR) può eseguire una Garbage Collection sugli oggetti quando il processo sottoposto a debug viene continuato. Il Garbage Collection può spostare gli oggetti in memoria. Un oggetto `ICorDebugReferenceValue` collaborerà con l'Garbage Collection in modo che le informazioni vengano aggiornate dopo l'Garbage Collection oppure verranno invalidate in modo implicito prima del Garbage Collection.  
  
 L' `ICorDebugReferenceValue` oggetto può essere invalidato in modo implicito dopo che è stato proseguito il processo sottoposto a debug. Il "ICorDebugHandleValue" derivato non viene invalidato fino a quando non viene rilasciato o esposto in modo esplicito.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
