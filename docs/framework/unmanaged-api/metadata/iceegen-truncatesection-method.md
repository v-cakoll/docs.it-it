---
title: Metodo ICeeGen::TruncateSection
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1036d6080bf17eea288724c7980ce53dfa2121f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116321"
---
# <a name="iceegentruncatesection-method"></a>Metodo ICeeGen::TruncateSection
Tronca la sezione di codice specificato per la lunghezza specificata.  
  
 Questo metodo è obsoleto e non deve essere utilizzato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `section`  
 [in] La sezione da troncare.  
  
 `len`  
 [in] La lunghezza, espressa in byte, da cui si desidera troncare la sezione.  
  
## <a name="remarks"></a>Note  
 Chiamare `TruncateSection` solo se si hanno requisiti di sezione speciale che non sono gestiti tramite altri metodi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
