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
ms.openlocfilehash: 99824e9a7fd759fb30bfa377156fc28eb934a2b4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212217"
---
# <a name="icordebugmodule2applychanges-method"></a>Metodo ICorDebugModule2::ApplyChanges
Applica le modifiche nei metadati e le modifiche nel codice MSIL (Microsoft Intermediate Language) al processo in esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cbMetadata`  
 in Dimensione, in byte, dei metadati delta.  
  
 `pbMetadata`  
 in Buffer contenente i metadati delta. L'indirizzo del buffer viene restituito dal metodo [IMetaDataEmit2:: SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md) .  
  
 Gli indirizzi virtuali relativi (RVA) nei metadati devono essere relativi all'inizio del codice MSIL.  
  
 `cbIL`  
 in Dimensione, in byte, del codice MSIL delta.  
  
 `pbIL`  
 in Buffer che contiene il codice MSIL aggiornato.  
  
## <a name="remarks"></a>Osservazioni  
 Il `pbMetadata` parametro è in un formato di metadati delta speciale (come output di [IMetaDataEmit2:: SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata`accetta i metadati precedenti come base e descrive le singole modifiche da applicare a tale base.  
  
 Al contrario, il `pbIL[` parametro] contiene il nuovo codice MSIL per il metodo aggiornato ed è destinato a sostituire completamente il codice MSIL precedente per tale metodo  
  
 Quando il codice MSIL delta e i metadati sono stati creati nella memoria del debugger, il debugger chiama `ApplyChanges` per inviare le modifiche nel Common Language Runtime (CLR). Il runtime aggiorna le tabelle di metadati, inserisce il nuovo codice MSIL nel processo e configura una compilazione JIT (just-in-Time) del nuovo MSIL. Una volta applicate le modifiche, il debugger deve chiamare [IMetaDataEmit2:: ResetENCLog](../metadata/imetadataemit2-resetenclog-method.md) per prepararsi alla successiva sessione di modifica. Il debugger può quindi continuare il processo.  
  
 Ogni volta che il debugger chiama `ApplyChanges` su un modulo con metadati delta, deve chiamare anche il metodo [IMetaDataEmit:: ApplyEditAndContinue](../metadata/imetadataemit-applyeditandcontinue-method.md) con gli stessi metadati delta in tutte le copie dei metadati del modulo, tranne la copia utilizzata per emettere le modifiche. Se una copia dei metadati diventa in qualche modo non sincronizzata con i metadati effettivi, il debugger può sempre eliminare la copia e ottenere una nuova copia.  
  
 Se il `ApplyChanges` metodo ha esito negativo, la sessione di debug si trova in uno stato non valido e deve essere riavviata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
