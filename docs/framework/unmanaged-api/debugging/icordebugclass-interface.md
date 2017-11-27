---
title: ICorDebugClass Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass
helpviewer_keywords: ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 79e93a44f2cc532286a7e9b01fa32292a4e1c69a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclass-interface1"></a>ICorDebugClass Interface1
Rappresenta un tipo, che può essere di base o complesso, ovvero definito dall'utente. Se il tipo è generico, `ICorDebugClass` rappresenta il tipo generico privo di istanze.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetModule (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Ottiene il modulo che definisce questa classe.|  
|[GetStaticFieldValue (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|Ottiene il valore del campo statico specificato.|  
|[GetToken (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|Ottiene il `TypeDef` token di metadati per questa classe.|  
  
## <a name="remarks"></a>Note  
 Il `ICorDebugClass` interfaccia rappresenta un tipo generico privo di istanze. ICorDebugType (interfaccia) rappresenta un tipo generico istanziato. Ad esempio, `Hashtable<K, V>` sarebbe rappresentato da `ICorDebugClass`, mentre `Hashtable<Int32, String>` sarebbe rappresentato da `ICorDebugType`.  
  
 I tipi non generici sono rappresentati da `ICorDebugClass` e `ICorDebugType`. L'interfaccia di quest'ultima è stato introdotto in .NET Framework versione 2.0 per gestire la creazione di istanze di tipo.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
