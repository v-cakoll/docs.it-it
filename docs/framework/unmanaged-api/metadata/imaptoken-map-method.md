---
title: Metodo IMapToken::Map
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ac12d5b6bc2911e3bd879285a9a12f65c426f0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745850"
---
# <a name="imaptokenmap-method"></a>Metodo IMapToken::Map
Esegue il mapping di una relazione tra gli assembly che utilizzano le firme di metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tkImp`  
 [in] Il token di metadati che rappresenta l'oggetto di codice importati.  
  
 `tkEmit`  
 [in] Il token di metadati che rappresenta l'oggetto di codice generato.  
  
## <a name="remarks"></a>Note  
 Quando la modifica del mapping dei token si verifica durante un'operazione di unione, il token originale è con ambito nell'ambito dei metadati importati (origine) e il nuovo token è con ambito nell'ambito dei metadati generato (destinazione).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
