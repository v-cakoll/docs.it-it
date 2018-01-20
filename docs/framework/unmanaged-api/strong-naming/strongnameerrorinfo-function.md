---
title: Funzione StrongNameErrorInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: StrongNameErrorInfo
helpviewer_keywords: StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e17ec04293f6274e307c66fc242c49bbdeee507
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
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
 La maggior parte dei metodi con nome sicuro restituisce una semplice `true` o `false` indicazione del completamento. Utilizzare il `StrongNameErrorInfo` funzione per recuperare un valore HRESULT che specifica l'ultimo errore generato dalle funzioni con nome sicuro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali di denominazione sicura](http://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
