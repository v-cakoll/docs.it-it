---
title: ICorDebugReferenceValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue
helpviewer_keywords: ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ac6260a601f7fdacf84034a6ae83c9423fafa11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevalue-interface1"></a>ICorDebugReferenceValue Interface1
Fornisce metodi che gestiscono un valore che è un riferimento a un oggetto. (Ovvero, questa interfaccia fornisce metodi che gestiscono un puntatore) Questa interfaccia implementa "ICorDebugValue".  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Dereference](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|Ottiene l'oggetto a cui fa riferimento.|  
|[Metodo DereferenceStrong](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|Non implementato. Non chiamare questo metodo.|  
|[Metodo GetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|Ottiene l'indirizzo di memoria corrente dell'oggetto di riferimento.|  
|[Metodo IsNull](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|Ottiene un valore che indica se questo `ICorDebugReferenceValue` è un valore null, nel qual caso il `ICorDebugReferenceValue` non punta a un oggetto.|  
|[Metodo SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|Imposta l'indirizzo di memoria corrente. Ovvero, questo metodo imposta `ICorDebugReferenceValue` in modo che punti a un oggetto.|  
  
## <a name="remarks"></a>Note  
 Common language runtime (CLR) può eseguire un'operazione di garbage collection sugli oggetti quando si continua il processo sottoposto a debug. Operazione di garbage collection può spostarsi oggetti in memoria. Un `ICorDebugReferenceValue` interagirà con l'operazione di garbage collection in modo che le relative informazioni viene aggiornate dopo l'operazione di garbage collection o verrà invalidato in modo implicito prima operazione di garbage collection.  
  
 Il `ICorDebugReferenceValue` oggetto può essere invalidato in modo implicito dopo il processo sottoposto a debug. "L'interfaccia ICorDebugHandleValue derivata" non viene invalidata fino a quando non viene rilasciata o esposta in modo esplicito.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
    
    
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
