---
title: Metodo IMetaDataImport::GetMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: 2cfb66203d8f2d69ea188f6913a5ef34dd74791e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503601"
---
# <a name="imetadataimportgetmethodsemantics-method"></a>Metodo IMetaDataImport::GetMethodSemantics
Ottiene i flag che indicano la relazione tra il metodo a cui fa riferimento il token MethodDef specificato e la proprietà abbinata e l'evento a cui fa riferimento il token EventProp specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mb`  
 in Token MethodDef che rappresenta il metodo per il quale ottenere le informazioni sul ruolo semantico.  
  
 `tkEventProp`  
 in Token che rappresenta la proprietà abbinata e l'evento per il quale ottenere il ruolo del metodo.  
  
 `pdwSemanticsFlags`  
 out Puntatore ai flag di semantica associati. Questo valore è una maschera di maschera dall'enumerazione [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) .  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo [IMetaDataEmit::D efineproperty](imetadataemit-defineproperty-method.md) imposta i flag di semantica di un metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
