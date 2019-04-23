---
title: Enumerazione WriteableMetadataUpdateMode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62e4328b75a7f6fecc28cd620ec3ac18460316c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111137"
---
# <a name="writeablemetadataupdatemode-enumeration"></a>Enumerazione WriteableMetadataUpdateMode
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Fornisce i valori che specificano se gli aggiornamenti in memoria ai metadati sono visibili a un debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a>Membri  
  
|Nome del membro|Descrizione|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|Mantiene la compatibilità con le versioni precedenti di .NET Framework quando vengono resi visibili gli aggiornamenti in memoria ai metadati. Per altre informazioni, vedere la sezione Osservazioni.|  
|`AlwaysShowUpdates`|Rende visibili al debugger gli aggiornamenti in memoria ai metadati.|  
  
## <a name="remarks"></a>Note  
 Un membro del `WriteableMetadataUpdateMode` enumerazione può essere passato per il [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) metodo per controllare se gli aggiornamenti in memoria ai metadati nel processo di destinazione sono visibili al debugger.  
  
 L'opzione `LegacyCompatPolicy` applica lo stesso comportamento delle versioni di .NET Framework precedenti alla 4.5.2. Spesso questo significa che i metadati degli aggiornamenti non sono visibili. Tuttavia, le chiamate a una serie di metodi di debug forzano in modo implicito il debugger a rendere visibili gli aggiornamenti. Ad esempio, se il debugger passa [ICorDebugILFrame:: GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) l'indice di una variabile non trovata nei metadati originali del metodo, tutti i metadati per il modulo viene aggiornato a uno snapshot corrispondente allo stato corrente del processo. In altre parole, con l'opzione `LegacyCompatPolicy` il debugger potrebbe visualizzare tutti gli aggiornamenti dei metadati disponibili, solo alcuni o nessuno, a seconda di come usa le altre parti dell'API di debug non gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Metodo SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
