---
title: Metodo IBindingDisplay::InitializeForProcess
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
ms.openlocfilehash: 8645878132359b6218cd62b1ff707208de53704b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442150"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>Metodo IBindingDisplay::InitializeForProcess
Inizializza l'oggetto [IBindingDisplay](ibindingdisplay-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pid`  
 in Identificatore del processo.  
  
## <a name="remarks"></a>Osservazioni  
 Il debugger chiama il `InitializeForProcess` metodo in fase di creazione per inizializzare la visualizzazione dell'associazione. `InitializeForProcess`deve essere chiamato in fase di creazione prima che venga chiamato un altro metodo su `IBindingDisplay` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** BindingDisplay. h  
  
 **Libreria:** BindingDisplay. idl  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IBindingDisplay](ibindingdisplay-interface.md)
