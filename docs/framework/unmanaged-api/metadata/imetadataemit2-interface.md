---
title: Interfaccia IMetaDataEmit2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 94180a1f844ac43d8a42be59ac4fca807a70ec70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2-interface"></a>Interfaccia IMetaDataEmit2
Estende il [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaccia principalmente per offrire la possibilità di utilizzare i tipi generici.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DefineGenericParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|Crea una definizione per un parametro di tipo generico e ottiene un token per tale parametro di tipo generico.|  
|[Metodo DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|Crea un'istanza generica di un metodo e ottiene un token per la definizione.|  
|[Metodo GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|Ottiene un valore che indica la differenza nelle dimensioni dei dati che sono necessario per esprimere le modifiche per la sessione di modifica e continuazione corrente.|  
|[Metodo ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|Reimposta il log di modifica e continuazione e avvia una nuova sessione.|  
|[Metodo SaveDelta](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|Salva le modifiche dalla sessione di modifica e continuazione corrente nel file specificato.|  
|[Metodo SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|Salva le modifiche dalla sessione corrente di modifica e continuazione in memoria.|  
|[Metodo SaveDeltaToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|Salva le modifiche dalla sessione di modifica e continuazione corrente nel flusso specificato.|  
|[Metodo SetGenericParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|Imposta i valori delle proprietà per la definizione di parametro generico a cui fa riferimento il token specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
