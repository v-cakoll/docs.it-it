---
title: 'Metodo IXCLRDataProcess:: GetAppDomainByUniqueId'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: bb02ffed09cbcc31e653bfd3165050c247908c5d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420784"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a>Metodo IXCLRDataProcess:: GetAppDomainByUniqueId

Ottiene un oggetto `AppDomain` in un processo in base al relativo identificatore univoco.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a>Parametri

`id`\
in Identificatore univoco di AppDomain

`appDomain`\
out AppDomain

## <a name="remarks"></a>Osservazioni

Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al ventesimo slot della tabella del metodo virtuale. L'oggetto `IXCLRDataAppDomain*` restituito viene usato per l'interazione con altre API.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).
**Intestazione:** Nessuna **libreria:** nessuna **.NET Framework versioni:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Interfaccia IXCLRDataProcess](ixclrdataprocess-interface.md)
