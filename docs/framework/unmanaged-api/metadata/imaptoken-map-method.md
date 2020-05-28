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
ms.openlocfilehash: 027694cee1b3e4d990796ba31300918f6d859679
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008196"
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
 in Token di metadati che rappresenta l'oggetto di codice importato.  
  
 `tkEmit`  
 in Token di metadati che rappresenta l'oggetto di codice emesso.  
  
## <a name="remarks"></a>Commenti  
 Quando il mapping del token viene eseguito durante un'operazione di merge, il token originale viene definito nell'ambito dei metadati importati (di origine) e l'ambito del nuovo token viene definito nell'ambito dei metadati generato (destinazione).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMapToken](imaptoken-interface.md)
