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
ms.openlocfilehash: 1bdaf6391ca5c19f073708d6258ad5775bec9824
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700733"
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

 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

 **Intestazione:** CorDebug. idl, CorDebug. h

 **Libreria** CorGuids.lib

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
 
