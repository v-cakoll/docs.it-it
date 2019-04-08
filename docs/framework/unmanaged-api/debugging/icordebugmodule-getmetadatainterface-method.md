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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37710fbb7acc50b80d7acebe4194b019c0b64660
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102596"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>Metodo ICorDebugModule::GetMetaDataInterface
Ottiene un oggetto di interfaccia di metadati che può essere utilizzato per esaminare i metadati per il modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `riid`  
 [in] L'ID di riferimento che specifica l'interfaccia dei metadati.  
  
 `ppObj`  
 [out] Un puntatore all'indirizzo di un `T:IUnknown` oggetto che rappresenta una delle [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).  
  
## <a name="remarks"></a>Note  
 Il debugger è possibile usare il `GetMetaDataInterface` metodo per creare una copia dei metadati originali di un modulo, che deve essere eseguita per modificare tale modulo. Il debugger chiama `GetMetaDataInterface` per ottenere un [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) oggetto dell'interfaccia per il modulo, quindi chiama [SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) per salvare una copia dei metadati del modulo in memoria.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metadati](../../../../docs/framework/unmanaged-api/metadata/index.md)
