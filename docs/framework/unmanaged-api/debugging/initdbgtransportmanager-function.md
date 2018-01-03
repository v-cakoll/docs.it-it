---
title: Funzione InitDbgTransportManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: InitDbgTransportManager
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37b849ed482f76692a63c70cbb0a3b9e1bacc8ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="initdbgtransportmanager-function"></a>Funzione InitDbgTransportManager
Inizializza il gestore trasporto per connettersi a una destinazione remota per l'enumerazione del runtime e dei processi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 Operazione completata.  
  
 E_OUTOFMEMORY  
 La funzione non è riuscita ad allocare memoria per un gestore trasporto.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Altri errori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** coreclrremotedebugginginterfaces. H  
  
 **Libreria:** mscordbi_macx86.dll  
  
 **Versioni di .NET framework:** 3.5 SP1
