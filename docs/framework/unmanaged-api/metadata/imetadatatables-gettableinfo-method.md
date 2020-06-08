---
title: Metodo IMetaDataTables::GetTableInfo
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
ms.openlocfilehash: 7e60dd9535809ca13f3bbe6ac76f5ea1209df734
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501172"
---
# <a name="imetadatatablesgettableinfo-method"></a>Metodo IMetaDataTables::GetTableInfo
Ottiene il nome, le dimensioni della riga, il numero di righe, il numero di colonne e l'indice della colonna chiave della tabella specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ixTbl`  
 in Identificatore della tabella le cui proprietà devono essere restituite.  
  
 `pcbRow`  
 out Puntatore alla dimensione, in byte, di una riga di tabella.  
  
 `pcRows`  
 out Puntatore al numero di righe nella tabella.  
  
 `pcCols`  
 out Puntatore al numero di colonne nella tabella.  
  
 `piKey`  
 out Puntatore all'indice della colonna chiave oppure-1 se la tabella non contiene colonne chiave.  
  
 `ppName`  
 out Puntatore a un puntatore al nome della tabella.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataTables](imetadatatables-interface.md)
- [Interfaccia IMetaDataTables2](imetadatatables2-interface.md)
