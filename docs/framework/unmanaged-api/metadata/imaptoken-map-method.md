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
ms.openlocfilehash: f2633bfadaabf208a2b86fda83375c3a136b93b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448172"
---
# <a name="imaptokenmap-method"></a>Metodo IMapToken::Map
Esegue il mapping di una relazione tra gli assembly che utilizzano le firme di metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tkImp`  
 [in] Il token di metadati che rappresenta l'oggetto codice importato.  
  
 `tkEmit`  
 [in] Il token di metadati che rappresenta l'oggetto di codice generato.  
  
## <a name="remarks"></a>Note  
 Quando il nuovo mapping dei token si verifica durante un'operazione di unione, il token originale è un ambito nell'ambito dei metadati importati (origine) e il nuovo token di ambito è nell'ambito dei metadati generato (destinazione).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
