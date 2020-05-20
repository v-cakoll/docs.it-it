---
title: Metodo IBindingDisplay::GetCurrentDisplay
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: 6fe8c3266a8c9a52cd1022589cd68485c4326fd1
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442189"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a>Metodo IBindingDisplay::GetCurrentDisplay
Restituisce le informazioni di visualizzazione dell'associazione corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `display`  
 [out, retval] Puntatore a un SafeArray contenente le informazioni di visualizzazione dell'associazione.  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo [IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) deve avere avuto esito positivo e il programma deve essere arrestato da un debugger.  
  
 Il chiamante deve deallocare la `SAFEARRAY` memoria restituita utilizzando [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** BindingDisplay. h  
  
 **Libreria:** BindingDisplay. idl  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IBindingDisplay](ibindingdisplay-interface.md)
- [Metodo InitializeForProcess](ibindingdisplay-initializeforprocess-method.md)
