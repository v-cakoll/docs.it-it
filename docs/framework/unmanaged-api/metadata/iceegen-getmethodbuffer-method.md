---
title: Metodo ICeeGen::GetMethodBuffer
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a093b18f72cc99c53951b3dc588ce0cff3c7fefd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="iceegengetmethodbuffer-method"></a>Metodo ICeeGen::GetMethodBuffer
Ottiene un buffer di dimensioni appropriate per il metodo all'indirizzo virtuale relativo specificato.  
  
 Questo metodo è obsoleto e non deve essere utilizzato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `RVA`  
 [in] L'indirizzo virtuale relativo del metodo per cui restituire un buffer.  
  
 `lpBuffer`  
 [out] Puntatore al buffer restituito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
