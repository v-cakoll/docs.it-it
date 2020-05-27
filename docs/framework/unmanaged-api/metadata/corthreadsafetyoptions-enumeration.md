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
ms.openlocfilehash: 8c0527a7bc3cde7344bf809dc8e6f5a3fac04852
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007507"
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
|`MDThreadSafetyDefault`|Valore predefinito. Come per `MDThreadSafetyOff`.|
|`MDThreadSafetyOff`|Indica che non è possibile impostare un blocco di lettura/scrittura.|
|`MDThreadSafetyOn`|Indica che è possibile impostare un blocco in lettura/scrittura.|

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** CorHdr. h

**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
