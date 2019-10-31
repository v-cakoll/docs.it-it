---
title: Metodo IAssemblyName::GetDisplayName
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
ms.openlocfilehash: 5dbb5dc483bc5a08c59606654d55b5a62266e509
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134376"
---
# <a name="iassemblynamegetdisplayname-method"></a>Metodo IAssemblyName::GetDisplayName
Ottiene il nome leggibile dell'assembly a cui fa riferimento questo oggetto [IAssemblyName](iassemblyname-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szDisplayName`  
 out Buffer di stringa che contiene il nome dell'assembly a cui si fa riferimento.  
  
 `pccDisplayName`  
 [in, out] Dimensioni del `szDisplayName` in caratteri wide, incluso un carattere di terminazione null.  
  
 `dwDisplayFlags`  
 in Combinazione bit per bit di valori [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) che influenzano le funzionalità di `szDisplayName`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyName](iassemblyname-interface.md)
- [Enumerazioni Fusion](fusion-enumerations.md)
