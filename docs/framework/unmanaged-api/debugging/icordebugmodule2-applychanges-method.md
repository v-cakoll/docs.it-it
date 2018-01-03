---
title: Metodo ICorDebugModule2::ApplyChanges
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.ApplyChanges
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4855b7a42d471304d000465a0437f29bdff05494
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2applychanges-method"></a>Metodo ICorDebugModule2::ApplyChanges
Applica le modifiche nei metadati e le modifiche nel codice Microsoft intermediate language (MSIL) per il processo in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cbMetadata`  
 [in] Dimensione, in byte, dei metadati delta.  
  
 `pbMetadata`  
 [in] Buffer che contiene i metadati delta. Viene restituito l'indirizzo del buffer dal [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) metodo.  
  
 Gli indirizzi virtuali relativi (RVA) nei metadati devono essere relativo all'inizio del codice MSIL.  
  
 `cbIL`  
 [in] Dimensione, in byte, del codice MSIL delta.  
  
 `pbIL`  
 [in] Buffer che contiene il codice MSIL aggiornato.  
  
## <a name="remarks"></a>Note  
 Il `pbMetadata` parametro è in un formato di metadati delta speciale (come output da [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata`accetta i metadati precedenti come base e descrive le singole modifiche da applicare alla base.  
  
 Al contrario, il `pbIL[`] parametro contiene il nuovo codice MSIL per il metodo aggiornato ed è concepito per sostituire completamente il precedente codice MSIL per il metodo  
  
 Quando il codice MSIL delta e i metadati sono stati creati in memoria del debugger, il debugger chiama `ApplyChanges` per inviare le modifiche in common language runtime (CLR). Il runtime aggiorna le relative tabelle di metadati, inserisce il codice MSIL di nuovo il processo e consente di impostare una compilazione di just-in-time (JIT) di tale codice. Una volta applicate le modifiche, il debugger deve chiamare [IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) per preparare per la sessione di modifica successiva. Il debugger può quindi continuare il processo.  
  
 Ogni volta che il debugger chiama `ApplyChanges` su un modulo che contiene metadati delta, deve anche chiamare [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) con gli stessi metadati delta su tutte le copie dei metadati del modulo, ad eccezione della copia utilizzato per generare le modifiche. In caso di una copia dei metadati in qualche modo di sincronizzazione con i metadati effettivi, il debugger può sempre eliminare tale copia e ottenere una nuova copia.  
  
 Se il `ApplyChanges` metodo ha esito negativo, il debug della sessione è in uno stato non valido e deve essere riavviata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
