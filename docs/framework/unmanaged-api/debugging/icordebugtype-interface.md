---
title: ICorDebugType Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType
helpviewer_keywords: ICorDebugType interface [.NET Framework debugging]
ms.assetid: 94e02e31-67ea-4b00-8148-a46740a4571d
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a25e72766e6647f820c9871e989d4b24db0bf26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtype-interface1"></a>ICorDebugType Interface1
Rappresenta un tipo di base o complesso (è definito dall'utente). Se il tipo è generico, `ICorDebugType` rappresenta il tipo generico di cui è stata creata un'istanza.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[EnumerateTypeParameters (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-enumeratetypeparameters-method.md)|Ottiene un puntatore a interfaccia a un'interfaccia ICorDebugTypeEnum che fa riferimento il tipo generico <xref:System.Type> parametri della classe a cui fa riferimento questo `ICorDebugType`.|  
|[GetBase (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getbase-method.md)|Ottiene un puntatore a interfaccia a un `ICorDebugType` che fa riferimento alla classe di base della classe a cui fa riferimento questo `ICorDebugType`, se presente.|  
|[GetClass (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)|Ottiene un puntatore a interfaccia ICorDebugClass che fa riferimento al costruttore tipizzato di `ICorDebugType`.|  
|[GetFirstTypeParameter (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getfirsttypeparameter-method.md)|Ottiene un puntatore a interfaccia a un `ICorDebugType` che fa riferimento il primo generico <xref:System.Type> parametro del costruttore della classe a cui fa riferimento questo `ICorDebugType`.|  
|[GetRank (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getrank-method.md)|Ottiene il numero di dimensioni in un tipo di matrice.|  
|[GetStaticFieldValue (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)|Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che contiene il valore del campo statico a cui fa riferimento il campo specificato token stack frame specificato.|  
|[GetType (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md)|Ottiene un valore CorElementType che descrive il tipo nativo di common language runtime <xref:System.Type> a cui fa riferimento questo `ICorDebugType`.|  
  
## <a name="remarks"></a>Note  
 Se il tipo è generico, `ICorDebugClass` rappresenta il tipo privo di istanze. Il `ICorDebugType` interfaccia rappresenta un tipo generico istanziato. Ad esempio, Hashtable\<K, V > viene rappresentato da `ICorDebugClass`, mentre Hashtable\<Int32, String > viene rappresentato da `ICorDebugType`.  
  
 I tipi non generici sono rappresentati da `ICorDebugClass` e `ICorDebugType`. L'interfaccia di quest'ultima è stato introdotto in .NET Framework versione 2.0 per gestire la creazione di istanze di tipo.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
