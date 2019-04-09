---
title: Metodo EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b419962982fc80591ed565cceb28afb88a39495e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199141"
---
# <a name="enumcustomattributes-method"></a>Metodo EnumCustomAttributes
Recupera gli attributi personalizzati a livello di assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `hEnum`  
 Handle dell'enumeratore.  
  
 `tkType`  
 Tipo degli attributi da enumerare. Usare `mdTokenNill` per tutti gli attributi.  
  
 `rCustomValues`  
 Riceve i token di attributi personalizzati.  
  
 `cMax`  
 Specifica la dimensione di `rCustomValues` matrice.  
  
 `pcCustomValues`  
 Facoltativamente, riceve il numero di valori del token.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede alink.h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [Interfaccia IALink2](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API Alink](../../../../docs/framework/unmanaged-api/alink/index.md)
