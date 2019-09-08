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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d696326ff8861ed8496474f76e9eaf89b4ead3e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795396"
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
 out Puntatore restituito `IInstallReferenceEnum` .  
  
 `pName`  
 in [IAssemblyName](iassemblyname-interface.md) che identifica l'assembly per il quale enumerare i riferimenti.  
  
 `dwFlags`  
 in Flag che influenzano il comportamento dell'enumeratore.  
  
 `pvReserved`  
 in Riservato per l'estendibilità futura. `pvReserved`deve essere un riferimento null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria** Fusion. dll e mscorwks. dll. Usare Fusion. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IInstallReferenceEnum](iinstallreferenceenum-interface.md)
- [Interfaccia IAssemblyName](iassemblyname-interface.md)
- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
