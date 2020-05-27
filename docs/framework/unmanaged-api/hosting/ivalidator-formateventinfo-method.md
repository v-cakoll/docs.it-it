---
title: Metodo IValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
ms.openlocfilehash: 0c60631b5e034bc46d74412440d35d526359d043
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008573"
---
# <a name="ivalidatorformateventinfo-method"></a>Metodo IValidator::FormatEventInfo
Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hVECode`  
 in Valore HRESULT passato al gestore degli errori di convalida.  
  
 `Context`  
 in `VEContext`Istanza di che contiene informazioni di contesto sull'errore di convalida.  
  
 `msg`  
 [in, out] Stringa che contiene il messaggio di errore restituito.  
  
 `ulMaxLength`  
 in Lunghezza massima del messaggio di errore.  
  
 `psa`  
 in Matrice sicura che contiene parametri aggiuntivi che descrivono l'errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** IValidator. idl, IValidator. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
