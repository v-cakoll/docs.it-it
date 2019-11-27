---
title: Enumerazione CorThreadSafetyOptions
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
ms.openlocfilehash: 93dd8c56176890d04d792f3c336492e4f232825b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442472"
---
# <a name="corthreadsafetyoptions-enumeration"></a>Enumerazione CorThreadSafetyOptions

Specifica i flag per selezionare le opzioni per la thread safety.

## <a name="syntax"></a>Sintassi

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a>Membri

|Membro|Descrizione|
|------------|-----------------|
|`MDThreadSafetyDefault`|Valore predefinito. Uguale a `MDThreadSafetyOff`.|
|`MDThreadSafetyOff`|Indica che non è possibile impostare un blocco di lettura/scrittura.|
|`MDThreadSafetyOn`|Indica che è possibile impostare un blocco in lettura/scrittura.|

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorHdr. h

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
