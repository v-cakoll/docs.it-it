---
title: Metodo ICorDebugModule::GetMetaDataInterface
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
ms.openlocfilehash: 8f3cc16054d4b5340c9460e9c3fbcba6e563567a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212555"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>Metodo ICorDebugModule::GetMetaDataInterface
Ottiene un oggetto di interfaccia di metadati che può essere utilizzato per esaminare i metadati per il modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `riid`  
 in ID di riferimento che specifica l'interfaccia dei metadati.  
  
 `ppObj`  
 out Puntatore all'indirizzo di un `T:IUnknown` oggetto che corrisponde a una delle interfacce di [metadati](../metadata/metadata-interfaces.md).  
  
## <a name="remarks"></a>Osservazioni  
 Il debugger può usare il `GetMetaDataInterface` metodo per creare una copia dei metadati originali per un modulo, che deve eseguire per modificare il modulo. Il debugger chiama `GetMetaDataInterface` per ottenere un oggetto di interfaccia [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) per il modulo, quindi chiama [IMetaDataEmit:: SaveToMemory](../metadata/imetadataemit-savetomemory-method.md) per salvare una copia dei metadati del modulo in memoria.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metadati](../metadata/index.md)
