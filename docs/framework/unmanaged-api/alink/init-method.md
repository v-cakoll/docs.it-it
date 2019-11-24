---
title: Metodo Init
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 986ae69e7ebb8f607be5d37fab426bcc787abb26
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445636"
---
# <a name="init-method"></a>Metodo Init
Prepara gli oggetti che implementano l' [Interfaccia IALink](ialink-interface.md) per l'utilizzo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a>Parametri  
 `pDispenser`  
 Puntatore all' [interfaccia IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) per il dispenser di metadati.  
  
 `pErrorHandler`  
 Puntatore all' [interfaccia IMetaDataError](../metadata/imetadataerror-interface.md) a un'interfaccia di gestione degli errori facoltativa.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 Richiede ALink. h  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
