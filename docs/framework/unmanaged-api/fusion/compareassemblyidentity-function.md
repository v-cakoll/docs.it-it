---
title: Funzione CompareAssemblyIdentity
ms.date: 03/30/2017
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
ms.openlocfilehash: f6711902fb9d5c5c16084057b731746843cf0230
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108915"
---
# <a name="compareassemblyidentity-function"></a>Funzione CompareAssemblyIdentity
Confronta due identità di assembly per determinare se sono equivalenti.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzAssemblyIdentity1`  
 in Identità testuale del primo assembly nel confronto.  
  
 `fUnified1`  
 in Flag booleano che indica l'unificazione specificata dall'utente per `pwzAssemblyIdentity1`.  
  
 `pwzAssemblyIdentity2`  
 in Identità testuale del secondo assembly nel confronto.  
  
 `fUnified2`  
 in Flag booleano che indica l'unificazione specificata dall'utente per `pwzAssemblyIdentity2`.  
  
 `pfEquivalent`  
 out Flag booleano che indica se i due assembly sono equivalenti.  
  
 `pResult`  
 out Enumerazione [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) che contiene informazioni dettagliate sul confronto.  
  
## <a name="return-value"></a>Valore restituito  
 `pfEquivalent` restituisce un valore booleano che indica se i due assembly sono equivalenti. `pResult` restituisce uno dei valori `AssemblyComparisonResult`, per fornire una ragione più dettagliata del valore di `pfEquivalent`.  
  
## <a name="remarks"></a>Note  
 `CompareAssemblyIdentity` controlla se `pwzAssemblyIdentity1` e `pwzAssemblyIdentity2` sono equivalenti. `pfEquivalent` è impostato su `true` in una o più delle condizioni seguenti:  
  
- Le due identità di assembly sono equivalenti. Per gli assembly con nome sicuro, l'equivalenza richiede che il nome dell'assembly, la versione, il token di chiave pubblica e le impostazioni cultura siano identici. Per gli assembly con nome semplice, l'equivalenza richiede una corrispondenza in base al nome e alle impostazioni cultura dell'assembly.  
  
- Entrambe le identità degli assembly fanno riferimento agli assembly eseguiti nel .NET Framework. Questa condizione restituisce `true` anche se i numeri di versione dell'assembly non corrispondono.  
  
- I due assembly non sono assembly gestiti, ma `fUnified1` o `fUnified2` è stato impostato su `true`.  
  
 Il flag `fUnified` indica che tutti i numeri di versione fino al numero di versione dell'assembly con nome sicuro sono considerati equivalenti all'assembly con nome sicuro. Se, ad esempio, il valore di `pwzAssemblyIndentity1` è "MyAssembly, Version = 3.0.0.0, Culture = neutral, publicKeyToken =...." e il valore di `fUnified1` è `true`, significa che tutte le versioni di MyAssembly dalla versione 0.0.0.0 a 3.0.0.0 devono essere considerate come equivalente. In tal caso, se `pwzAssemblyIndentity2` fa riferimento allo stesso assembly `pwzAssemblyIndentity1`, ad eccezione del fatto che ha un numero di versione inferiore, `pfEquivalent` viene impostato su `true`. Se `pwzAssemblyIdentity2` fa riferimento a un numero di versione superiore, `pfEquivalent` viene impostato su `true` solo se il valore di `fUnified2` è `true`.  
  
 Il parametro `pResult` include informazioni specifiche sui motivi per cui i due assembly sono considerati equivalenti o non equivalenti. Per ulteriori informazioni, vedere [Enumerazione AssemblyComparisonResult](assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
- [Enumerazione AssemblyComparisonResult](assemblycomparisonresult-enumeration.md)
