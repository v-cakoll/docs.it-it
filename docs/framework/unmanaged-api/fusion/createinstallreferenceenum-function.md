---
title: Funzione CreateInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: f089769f854bad5d3e572e0307734e06e72ca89c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108562"
---
# <a name="createinstallreferenceenum-function"></a>Funzione CreateInstallReferenceEnum
Ottiene un puntatore a un'istanza di [IInstallReferenceEnum](iinstallreferenceenum-interface.md) che rappresenta un elenco di riferimenti di un'applicazione all'assembly specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `ppRefEnum`  
 out Puntatore `IInstallReferenceEnum` restituito.  
  
 `pName`  
 in [IAssemblyName](iassemblyname-interface.md) che identifica l'assembly per il quale enumerare i riferimenti.  
  
 `dwFlags`  
 in Flag che influenzano il comportamento dell'enumeratore.  
  
 `pvReserved`  
 in Riservato per l'estendibilità futura. `pvReserved` deve essere un riferimento null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Fusion. dll e mscorwks. dll. Usare Fusion. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IInstallReferenceEnum](iinstallreferenceenum-interface.md)
- [Interfaccia IAssemblyName](iassemblyname-interface.md)
- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
