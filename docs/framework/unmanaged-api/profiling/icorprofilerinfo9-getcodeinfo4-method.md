---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 3e3e3afc221d153ff3573126ff10014d39af761a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868304"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a>Metodo ICorProfilerInfo9:: GetCodeInfo4

Dato l'indirizzo iniziale del codice nativo, restituisce i blocchi di memoria virtuale che archiviano il codice.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a>Parametri

- `pNativeCodeStartAddress`

  \[in] puntatore all'inizio di una funzione nativa.

- `cCodeInfos`

  \[in] la dimensione della matrice di `codeInfos`.

- `pcCodeInfos`

  \[out] puntatore al numero totale di strutture [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) disponibili.

- `codeInfos`

  \[out] buffer fornito dal chiamante. Una volta completato, il metodo contiene una matrice di strutture `COR_PRF_CODE_INFO`, ognuna delle quali descrive un blocco di codice nativo.

## <a name="remarks"></a>Note

Il `GetCodeInfo4` metodo è simile a [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), con la differenza che è possibile cercare informazioni sul codice per versioni native diverse di un metodo.

> [!NOTE]
> `GetCodeInfo4` possibile attivare una Garbage Collection.

Gli ambiti vengono ordinati in sequenza crescente in base all'offset CIL (Common Intermediate Language).

Quando `GetCodeInfo4` restituisce, è necessario verificare che il buffer di `codeInfos` sia sufficientemente grande da contenere tutte le strutture di [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) . A tale scopo, confrontare il valore di `cCodeInfos` con il valore del parametro `cchName`. Se `cCodeInfos` diviso per la dimensione di una struttura [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) è inferiore a `pcCodeInfos`, allocare un `codeInfos` buffer più grande, aggiornare `cCodeInfos` con la nuova dimensione maggiore e chiamare `GetCodeInfo4` di nuovo.

In alternativa, è possibile chiamare innanzitutto `GetCodeInfo4` con un buffer `codeInfos` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer `codeInfos` sul valore restituito in `pcCodeInfos`, moltiplicato per la dimensione di una struttura [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) e chiamare nuovamente `GetCodeInfo4`.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo9](ICorProfilerInfo9-interface.md)
