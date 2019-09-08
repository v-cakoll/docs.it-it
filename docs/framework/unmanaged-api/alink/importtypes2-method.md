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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce09eca30e1edb9e1afc02216a07955a5fed4fd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787264"
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
