---
title: Metodo ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d64773aa0d35f2e97232576d145dfcba624812ec
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395534"
---
# <a name="icordebugcode2getcodechunks-method"></a>Metodo ICorDebugCode2::GetCodeChunks

Ottiene i blocchi di codice di cui questo oggetto di codice è composto.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a>Parametri

`cbufSize`  
in Dimensione della matrice `chunks`.

`pcnumChunks`  
out Numero di blocchi restituiti nella matrice `chunks`.

`chunks`  
out Matrice di strutture "CodeChunkInfo", ognuna delle quali rappresenta un singolo blocco di codice. Se il valore di `cbufSize` è 0, questo parametro può essere null.

## <a name="remarks"></a>Note

I blocchi di codice non si sovrappongono mai e seguiranno l'ordine in cui sono stati concatenati da [ICorDebugCode:: GetCode](icordebugcode-getcode-method.md). Un oggetto di codice MSIL (Microsoft Intermediate Language) in .NET Framework versione 2,0 costituirà un singolo blocco di codice.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
