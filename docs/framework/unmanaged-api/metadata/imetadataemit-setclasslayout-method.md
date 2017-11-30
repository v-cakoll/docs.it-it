---
title: Metodo IMetaDataEmit::SetClassLayout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a68d94cbea408bee90b117965f83f760ba7ea5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetclasslayout-method"></a>Metodo IMetaDataEmit::SetClassLayout
Completa il layout dei campi per una classe che è stato definito da una precedente chiamata a [metodo DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Un `mdTypeDef` token che specifica la classe a disposizione.  
  
 `dwPackSize`  
 [in] La dimensione di compressione: 1, 2, 4, 8 o 16 byte. La dimensione di compressione è il numero di byte tra campi adiacenti.  
  
 `rFieldOffsets`  
 [in] Matrice di [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) strutture, ognuno dei quali specifica un campo della classe e il campo dell'offset all'interno della classe. Terminare la matrice con `mdTokenNil`.  
  
 `ulClassSize`  
 [in] Le dimensioni in byte, della classe.  
  
## <a name="remarks"></a>Note  
 Inizialmente è definita la classe chiamando il [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) metodo e specificando uno dei tre layout per i campi della classe: automatico, sequenziale o esplicito. In genere, si usano il layout automatico e consentire il runtime di scegliere il modo migliore per disporre i campi.  
  
 Tuttavia, è consigliabile che i campi disposti in base alla disposizione non gestito a codice viene utilizzato. In questo caso, scegliere il layout sequenziale o esplicito e chiamare `SetClassLayout` per completare il layout dei campi:  
  
-   Layout sequenziale: specificare la dimensione di compressione. Un campo è allineato in base alle dimensioni naturali o la dimensione di compressione, a seconda del valore comporta l'offset del campo inferiore. Impostare `rFieldOffsets` e `ulClassSize` a zero.  
  
-   Layout esplicito: specificare l'offset di ogni campo o specificare le dimensioni di classe e la dimensione di compressione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataEmit (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
