---
title: Funzione CompareAssemblyIdentity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 266868a65a0db75b57d46d92a469b4b6ceaa88e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="compareassemblyidentity-function"></a>Funzione CompareAssemblyIdentity
Confronta due identità di assembly per determinare se sono equivalenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a>Parametri  
 `pwzAssemblyIdentity1`  
 [in] Identità testuale del primo assembly nel confronto.  
  
 `fUnified1`  
 [in] Flag booleano che indica l'unificazione specificata dall'utente per `pwzAssemblyIdentity1`.  
  
 `pwzAssemblyIdentity2`  
 [in] Identità testuale del secondo assembly nel confronto.  
  
 `fUnified2`  
 [in] Flag booleano che indica l'unificazione specificata dall'utente per `pwzAssemblyIdentity2`.  
  
 `pfEquivalent`  
 [out] Flag booleano che indica se i due assembly sono equivalenti.  
  
 `pResult`  
 [out] Un [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumerazione che contiene informazioni dettagliate sul confronto.  
  
## <a name="return-value"></a>Valore restituito  
 `pfEquivalent`Restituisce un valore booleano che indica se i due assembly sono equivalenti. `pResult`Restituisce uno del `AssemblyComparisonResult` valori, per fornire più dettagliate sul motivo per il valore di `pfEquivalent`.  
  
## <a name="remarks"></a>Note  
 `CompareAssemblyIdentity`Controlla se `pwzAssemblyIdentity1` e `pwzAssemblyIdentity2` sono equivalenti. `pfEquivalent`è impostato su `true` in uno o più delle condizioni seguenti:  
  
-   Le due identità assembly sono equivalenti. Per l'assembly con nome sicuro, equivalenza richiede il nome dell'assembly, versione, token di chiave pubblica e impostazioni cultura in modo identico. Per l'assembly con nome semplice, equivalenza richiede una corrispondenza nel nome dell'assembly e delle impostazioni cultura.  
  
-   Entrambe le identità assembly fare riferimento ad assembly in esecuzione su .NET Framework. Questa condizione restituisce `true` anche se i numeri di versione di assembly non corrispondono.  
  
-   I due assembly non sono gestiti, ma `fUnified1` o `fUnified2` è stato impostato su `true`.  
  
 Il `fUnified` flag indica che tutti i numeri di versione fino al numero di versione di assembly con nome sicuro sono considerati equivalenti all'assembly con nome sicuro. Ad esempio, se il valore di `pwzAssemblyIndentity1` è "MyAssembly, versione = 3.0.0.0, culture = neutral, publicKeyToken =..." e il valore di `fUnified1` è `true`, ciò indica che tutte le versioni di MyAssembly tra 0.0.0.0 e 3.0.0.0 devono essere considerati equivalenti. In tal caso, se `pwzAssemblyIndentity2` fa riferimento allo stesso assembly come `pwzAssemblyIndentity1`, ad eccezione del fatto che disponga di un numero di versione, `pfEquivalent` è impostato su `true`. Se `pwzAssemblyIdentity2` fa riferimento a un numero di versione superiore, `pfEquivalent` è impostato su `true` solo se il valore di `fUnified2` è `true`.  
  
 Il `pResult` parametro contiene informazioni specifiche sui motivi per cui i due assembly sono considerati equivalente o non è equivalente. Per ulteriori informazioni, vedere [enumerazione AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [Enumerazione AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
