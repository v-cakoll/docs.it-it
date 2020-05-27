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
ms.openlocfilehash: a18583ce807ffa672811f3a0cd1e744233f6eb30
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008831"
---
# <a name="imetadataemitsetclasslayout-method"></a>Metodo IMetaDataEmit::SetClassLayout
Completa il layout dei campi per una classe definita da una chiamata precedente al [Metodo DefineTypeDef](imetadataemit-definetypedef-method.md).  
  
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
 in `mdTypeDef`Token che specifica la classe da disposte.  
  
 `dwPackSize`  
 in Dimensioni di compressione: 1, 2, 4, 8 o 16 byte. La dimensione di compressione è il numero di byte tra i campi adiacenti.  
  
 `rFieldOffsets`  
 in Matrice di strutture di [COR_FIELD_OFFSET](cor-field-offset-structure.md) , ognuna delle quali specifica un campo della classe e l'offset del campo all'interno della classe. Terminare la matrice con `mdTokenNil` .  
  
 `ulClassSize`  
 in Dimensione, in byte, della classe.  
  
## <a name="remarks"></a>Commenti  
 La classe viene definita inizialmente chiamando il metodo [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md) e specificando uno dei tre layout per i campi della classe: automatico, sequenziale o esplicito. In genere, è possibile usare il layout automatico e consentire al runtime di scegliere il modo migliore per disporre i campi.  
  
 Tuttavia, è possibile che i campi siano disposti in base alla disposizione utilizzata dal codice non gestito. In questo caso, scegliere layout sequenziale o esplicito e chiamare `SetClassLayout` per completare il layout dei campi:  
  
- Layout sequenziale: specificare le dimensioni di compressione. Un campo è allineato in base alla dimensione naturale o alla dimensione di compressione, a seconda del risultato dell'offset minore del campo. Impostare `rFieldOffsets` e `ulClassSize` su zero.  
  
- Layout esplicito: specificare l'offset di ogni campo o specificare le dimensioni della classe e le dimensioni di compressione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
