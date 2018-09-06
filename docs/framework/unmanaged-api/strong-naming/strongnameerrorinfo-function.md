---
title: Funzione StrongNameErrorInfo
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ad328d484ba01e22557d7d23d1cfa21813de9c8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43860337"
---
# <a name="strongnameerrorinfo-function"></a>Funzione StrongNameErrorInfo
Ottiene l'ultimo codice di errore che è stato generato da una delle funzioni con nome sicuro.  
  
 Questa funzione è stata deprecata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>Valore restituito  
 L'ultimo codice di errore COM impostato da una delle funzioni con nome sicuro.  
  
## <a name="remarks"></a>Note  
 La maggior parte dei metodi con nome sicuro restituiscono un semplice `true` o `false` indicazione del completamento. Usare il `StrongNameErrorInfo` funzione per recuperare un valore HRESULT che specifica l'ultimo errore generato dalle funzioni con nome sicuro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali per la gestione del nome sicuro](https://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
