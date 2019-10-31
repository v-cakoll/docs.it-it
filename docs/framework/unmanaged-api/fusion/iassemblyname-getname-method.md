---
title: Metodo IAssemblyName::GetName
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
ms.openlocfilehash: 5f758d76d779cff7db119e69dc1cf3342071f1c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134342"
---
# <a name="iassemblynamegetname-method"></a>Metodo IAssemblyName::GetName
Ottiene il nome semplice e non crittografato dell'assembly a cui fa riferimento questo oggetto [IAssemblyName](iassemblyname-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `lpcwBuffer`  
 [in, out] Dimensioni del `pwzName` in caratteri wide, incluso il carattere di terminazione null.  
  
 `pwzName`  
 out Buffer che consente di memorizzare il nome dell'assembly a cui si fa riferimento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IAssemblyName](iassemblyname-interface.md)
