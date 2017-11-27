---
title: Metodo ICorDebugThread4::GetBlockingObjects
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.GetBlockingObjects Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6783d7f9af67acdff147cc46ea4f856f9b10bf3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4getblockingobjects-method"></a>Metodo ICorDebugThread4::GetBlockingObjects
Fornisce un'enumerazione ordinata di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture che forniscono informazioni di blocco del thread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppBlockingObjectEnum`  
 [out] Un puntatore a un'enumerazione ordinata di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.  
  
## <a name="remarks"></a>Note  
 Il primo elemento nell'enumerazione restituita corrisponde alla struttura prima che blocca il thread. Il secondo elemento corrisponde a un elemento di blocco che viene rilevato durante l'esecuzione di una chiamata di procedura asincrona (APC) quando bloccato sul primo e così via.  
  
 L'enumerazione è valida solo per la durata dello stato di sincronizzazione corrente.  
  
 Questo metodo deve essere chiamato mentre l'oggetto del debug è in uno stato sincronizzato.  
  
 Se `ppBlockingObjectEnum` non è un puntatore valido, il risultato è indefinito.  
  
 Se un thread è bloccato e non può essere determinato l'errore, il metodo restituisce un HRESULT che indica un errore. in caso contrario, viene restituito S_OK.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugThread4 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
