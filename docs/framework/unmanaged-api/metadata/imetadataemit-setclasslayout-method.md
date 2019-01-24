---
title: Metodo IMetaDataEmit::SetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2dc1664551683066a33fb52e16e4909506601f2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588691"
---
# <a name="imetadataemitsetclasslayout-method"></a>Metodo IMetaDataEmit::SetClassLayout
Completa il layout dei campi per una classe che è stato definito da una chiamata precedente a [metodo DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
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
 [in] Un `mdTypeDef` token che specifica la classe disposizione.  
  
 `dwPackSize`  
 [in] La dimensione di compressione: 1, 2, 4, 8 o 16 byte. La dimensione di compressione è il numero di byte tra i campi adiacenti.  
  
 `rFieldOffsets`  
 [in] Matrice di [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) strutture, ognuno dei quali specifica un campo della classe e il campo dell'offset all'interno della classe. Terminare la matrice con `mdTokenNil`.  
  
 `ulClassSize`  
 [in] Le dimensioni, in byte, della classe.  
  
## <a name="remarks"></a>Note  
 La classe viene definita inizialmente chiamando il [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) metodo e specificando uno dei tre layout per i campi della classe: automatici, sequenziale o esplicito. In genere, di usare un layout automatico e consentire il runtime di scegliere il modo migliore per disporre i campi.  
  
 Tuttavia, è possibile che i campi disposti in base alla disposizione che non gestiti di codice viene utilizzato. In questo caso, scegliere il layout sequenziale o esplicito e chiamata `SetClassLayout` per completare il layout dei campi:  
  
-   Layout sequenziale: Specificare la dimensione di compressione. Un campo è allineato in base alle dimensioni naturali o la dimensione di compressione, qualunque sia il risultati in più piccoli offset del campo. Impostare `rFieldOffsets` e `ulClassSize` su zero.  
  
-   Layout esplicito: Specificare l'offset di ogni campo o specificare le dimensioni di classe e la dimensione di compressione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
