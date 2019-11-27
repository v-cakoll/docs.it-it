---
title: Metodo ImportTypes2
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: 8dae903ab76ab83ac0818c4bc4a76e81094bdf65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445672"
---
# <a name="importtypes2-method"></a>Metodo ImportTypes2
Avvia l'importazione di tipi. Chiamare questo metodo per iniziare a importare i tipi da ogni ambito importato tramite il [metodo ImportFile](importfile-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `AssemblyID`  
 ID dell'assembly in cui eseguire l'importazione.  
  
 `FileToken`  
 ID del file da importare.  
  
 `dwScope`  
 Ambito in base zero da cui eseguire l'importazione.  
  
 `phEnum`  
 Riceve l'handle dell'enumeratore per i tipi nell'ambito specificato.  
  
 `ppImportScope`  
 Riceve facoltativamente l'interfaccia dell' [interfaccia IMetaDataImport2](../metadata/imetadataimport2-interface.md) .  
  
 `pdwCountOfTypes`  
 Riceve facoltativamente il numero di tipi nell'ambito specificato.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink2](ialink2-interface.md)
- [Interfaccia IALink](ialink-interface.md)
- [Alink (API)](index.md)
