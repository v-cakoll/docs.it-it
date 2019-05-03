---
title: Metodo ICorDebugModule2::ApplyChanges
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab0e28bd21b66f370a1a1e82359fe474574fd7bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987962"
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
  
## <a name="parameters"></a>Parametri  
 `cbMetadata`  
 [in] Dimensione, espressa in byte, dei metadati del delta.  
  
 `pbMetadata`  
 [in] Buffer che contiene i metadati del delta. Viene restituito l'indirizzo del buffer dal [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) (metodo).  
  
 Gli indirizzi virtuali relativi (RVA) nei metadati devono essere relativo all'inizio del codice MSIL.  
  
 `cbIL`  
 [in] Dimensione, in byte, del codice MSIL delta.  
  
 `pbIL`  
 [in] Buffer che contiene il codice MSIL aggiornato.  
  
## <a name="remarks"></a>Note  
 Il `pbMetadata` parametro è in un formato di metadati speciale delta (come output dal [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata` accetta i metadati precedenti come base e vengono descritte le singole modifiche da applicare alla base.  
  
 Al contrario, il `pbIL[`] parametro contiene il nuovo codice MSIL per il metodo aggiornato ed è concepito per sostituire completamente il precedente codice MSIL per il metodo  
  
 Quando il delta MSIL e i metadati sono stati creati in memoria del debugger, il debugger chiama `ApplyChanges` per inviare le modifiche in common language runtime (CLR). Il runtime aggiorna le relative tabelle di metadati, inserisce il codice MSIL di nuovo nel processo e consente di impostare una compilazione JIT just-in-time del nuovo codice MSIL. Quando le modifiche sono state applicate, il debugger deve chiamare [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) preparare per la sessione di modifica successiva. Il debugger può continuare il processo.  
  
 Ogni volta che il debugger chiama `ApplyChanges` su un modulo che include metadati differenziali, questo deve chiamare anche [ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) con gli stessi metadati delta in tutte le copie dei metadati del modulo, ad eccezione della copia utilizzato per generare le modifiche. Se una copia dei metadati non è più in qualche modo di sincronizzato con i metadati effettivi, il debugger può sempre sbarazzarsi di tale copia e ottenere una nuova copia.  
  
 Se il `ApplyChanges` metodo ha esito negativo, il debug della sessione è in uno stato non valido e deve essere riavviata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
