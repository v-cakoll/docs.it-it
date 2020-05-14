---
title: 'Metodo IXCLRDataModule:: GetMethodDefinitionByToken'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c70920205b27376d453bdd0a13223c6a5569075b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395290"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a>Metodo IXCLRDataModule:: GetMethodDefinitionByToken

Ottiene la definizione del metodo corrispondente a un token di metadati specificato.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a>Parametri

`token`\
in Token del metodo.

`methodDefinition`\
out Definizione del metodo.

## <a name="remarks"></a>Commenti

Il metodo fornito fa parte dell' `IXCLRDataModule` interfaccia e corrisponde allo slot 26 della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedi anche

- [Debug](index.md)
- [Interfaccia IXCLRDataModule](ixclrdatamodule-interface.md)
