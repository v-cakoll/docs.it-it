---
title: Interfaccia IMetaDataEmit2
ms.date: 03/30/2017
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
ms.openlocfilehash: 5a232f30da8812c6f3bd94647d74151312a8593b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493039"
---
# <a name="imetadataemit2-interface"></a>Interfaccia IMetaDataEmit2
Estende l'interfaccia [IMetaDataEmit](imetadataemit-interface.md) principalmente per consentire l'utilizzo di tipi generici.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DefineGenericParam](imetadataemit2-definegenericparam-method.md)|Crea una definizione per un parametro di tipo generico e ottiene un token per il parametro di tipo generico.|  
|[Metodo DefineMethodSpec](imetadataemit2-definemethodspec-method.md)|Crea un'istanza generica di un metodo e ottiene un token per la definizione.|  
|[Metodo GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md)|Ottiene un valore che indica la differenza tra le dimensioni dei dati necessari per esprimere le modifiche per la sessione di modifica e continuazione corrente.|  
|[Metodo ResetENCLog](imetadataemit2-resetenclog-method.md)|Reimposta il log di modifica e continuazione e avvia una nuova sessione.|  
|[Metodo SaveDelta](imetadataemit2-savedelta-method.md)|Salva le modifiche dalla sessione di modifica e continuazione corrente nel file specificato.|  
|[Metodo SaveDeltaToMemory](imetadataemit2-savedeltatomemory-method.md)|Salva le modifiche dalla sessione di modifica e continuazione corrente alla memoria.|  
|[Metodo SaveDeltaToStream](imetadataemit2-savedeltatostream-method.md)|Salva le modifiche dalla sessione di modifica e continuazione corrente nel flusso specificato.|  
|[Metodo SetGenericParamProps](imetadataemit2-setgenericparamprops-method.md)|Imposta i valori delle proprietà per la definizione di parametro generico a cui fa riferimento il token specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](metadata-interfaces.md)
- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
