---
title: IXCLRDataProcess::GetAppDomainByUniqueId Method
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
ms.openlocfilehash: cf610e3af26c60dd9bf738bff8785890394d0f34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710274"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a>IXCLRDataProcess::GetAppDomainByUniqueId Method

Ottiene un `AppDomain` in un processo in base al relativo identificatore univoco.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

### <a name="parameters"></a>Parametri
`id` [in] L'identificatore univoco del dominio applicazione

`appDomain` [out] Dominio dell'applicazione

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 20 ° slot della tabella di metodo virtuale. Il `IXCLRDataAppDomain*` restituito viene usato per l'interazione con altre API.

## <a name="requirements"></a>Requisiti
**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria:** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [IXCLRDataProcess Interface](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
