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
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177567"
---
# <a name="imetadataemitsetclasslayout-method"></a>Metodo IMetaDataEmit::SetClassLayout
Completa il layout dei campi per una classe definita da una precedente chiamata al metodo [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 [in] Token `mdTypeDef` che specifica la classe da disporre.  
  
 `dwPackSize`  
 [in] La dimensione di compressione: 1, 2, 4, 8 o 16 byte. La dimensione di compressione è il numero di byte tra i campi adiacenti.  
  
 `rFieldOffsets`  
 [in] Matrice di [strutture COR_FIELD_OFFSET,](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) ognuna delle quali specifica un campo della classe e l'offset del campo all'interno della classe. Terminare la `mdTokenNil`matrice con .  
  
 `ulClassSize`  
 [in] Dimensione, in byte, della classe.  
  
## <a name="remarks"></a>Osservazioni  
 La classe viene inizialmente definita chiamando il metodo [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) e specificando uno dei tre layout per i campi della classe: automatico, sequenziale o esplicito. In genere, è necessario utilizzare il layout automatico e lasciare che il runtime scelga il modo migliore per definire il layout dei campi.  
  
 Tuttavia, è possibile che si desideri che i campi vengano disposti in base alla disposizione utilizzata dal codice non gestito. In questo caso, scegliere il layout `SetClassLayout` sequenziale o esplicito e chiamare per completare il layout dei campi:  
  
- Layout sequenziale: specificare le dimensioni di imballaggio. Un campo viene allineato in base alle dimensioni naturali o alle dimensioni di imballaggio, a seconda dell'offset più piccolo del campo. `rFieldOffsets` Impostare `ulClassSize` e a zero.  
  
- Layout esplicito: specificare l'offset di ogni campo o specificare la dimensione della classe e la dimensione di compressione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
