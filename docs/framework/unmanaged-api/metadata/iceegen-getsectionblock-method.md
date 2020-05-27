---
title: Metodo ICeeGen::GetSectionBlock
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: ed534890fc90d3b8543a1166c85903f10163f0a8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008323"
---
# <a name="iceegengetsectionblock-method"></a>Metodo ICeeGen::GetSectionBlock
Ottiene un blocco di sezione della codebase.  
  
 Questo metodo è obsoleto e non deve essere utilizzato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a>Parametri  
 `section`  
 in Sezione da cui recuperare un blocco della codebase.  
  
 `len`  
 in Lunghezza del blocco da recuperare.  
  
 `align`  
 in Byte, relativo all'inizio della sezione, con cui allineare il primo byte del blocco. Si tratta della posizione del blocco all'interno della sezione.  
  
 `ppBytes`  
 out Puntatore a una posizione che riceve l'indirizzo del blocco recuperato.  
  
## <a name="remarks"></a>Commenti  
 Chiamare `GetSectionBlock` solo se si dispone di requisiti speciali per la sezione che non sono gestiti da altri metodi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICeeGen](iceegen-interface.md)
