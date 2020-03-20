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
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176071"
---
# <a name="imaptokenmap-method"></a>Metodo IMapToken::Map
Esegue il mapping di una relazione tra gli assembly utilizzando le firme dei metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `tkImp`  
 [in] Token di metadati che rappresenta l'oggetto di codice importato.  
  
 `tkEmit`  
 [in] Token di metadati che rappresenta l'oggetto di codice generato.  
  
## <a name="remarks"></a>Osservazioni  
 Quando il rimappatura del token si verifica durante un'unione, l'ambito del token originale viene definito nell'ambito dei metadati importati (origine) e il nuovo token viene definito nell'ambito dei metadati generato (destinazione).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
