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
ms.openlocfilehash: 5c3f2f7a9c0804b71c9c8a52bb032aca7c03825e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790297"
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
  
|Nome membro|Descrizione|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|Mantiene la compatibilità con le versioni precedenti di .NET Framework quando vengono resi visibili gli aggiornamenti in memoria ai metadati. Per altre informazioni, vedere la sezione Osservazioni.|  
|`AlwaysShowUpdates`|Rende visibili al debugger gli aggiornamenti in memoria ai metadati.|  
  
## <a name="remarks"></a>Note  
 Un membro dell'enumerazione `WriteableMetadataUpdateMode` può essere passato al metodo [SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md) per controllare se gli aggiornamenti in memoria ai metadati nel processo di destinazione sono visibili al debugger.  
  
 L'opzione `LegacyCompatPolicy` applica lo stesso comportamento delle versioni di .NET Framework precedenti alla 4.5.2. Spesso questo significa che i metadati degli aggiornamenti non sono visibili. Tuttavia, le chiamate a una serie di metodi di debug forzano in modo implicito il debugger a rendere visibili gli aggiornamenti. Se, ad esempio, il debugger passa [ICorDebugILFrame:: GetLocalVariable](icordebugilframe-getlocalvariable-method.md) , l'indice di una variabile non è stato trovato nei metadati originali del metodo, tutti i metadati per il modulo vengono aggiornati a uno snapshot corrispondente allo stato corrente del processo. In altre parole, con l'opzione `LegacyCompatPolicy` il debugger potrebbe visualizzare tutti gli aggiornamenti dei metadati disponibili, solo alcuni o nessuno, a seconda di come usa le altre parti dell'API di debug non gestito.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Metodo SetWriteableMetadataUpdateMode](icordebugprocess7-setwriteablemetadataupdatemode-method.md)
