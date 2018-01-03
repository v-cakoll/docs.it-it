---
title: Funzioni di callback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4f39160e817ce04c5c15fb8299852a052d36c25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="callback-functions"></a>Funzioni di callback
Una funzione di callback è il codice di un'applicazione gestita che agevola una funzione di DLL non gestita nel completamento di un'attività. Le chiamate a una funzione di callback passano indirettamente da un'applicazione gestita a una funzione di DLL, per poi tornare nuovamente all'implementazione gestita. Alcune delle numerose funzioni di DLL chiamate tramite platform invoke richiedono, per essere eseguite in modo corretto, una funzione di callback nel codice gestito.  
  
 Nella maggior parte dei casi, per chiamare una funzione di DLL dal codice gestito, si crea e si usa una definizione gestita della funzione. Il processo è semplice.  
  
 L'utilizzo di una funzione di DLL che richiede una funzione di callback prevede alcuni passaggi aggiuntivi. In primo luogo è necessario determinare se la funzione richiede un callback controllando la documentazione relativa alla funzione. Successivamente occorre creare la funzione di callback nell'applicazione gestita. Infine si chiama la funzione di DLL passandole come argomento un puntatore alla funzione di callback. La figura seguente illustra una sintesi di questi passaggi.  
  
 ![Callback di platform invoke](../../../docs/framework/interop/media/pinvokecallback.gif "pinvokecallback")  
Funzione di callback e implementazione  
  
 Le funzioni di callback sono ideali per i casi in cui un'attività viene eseguita ripetutamente. Un altro utilizzo comune è quello con le funzioni di enumerazione, come **EnumFontFamilies**, **EnumPrinters** e **EnumWindows** nell'API Win32. La funzione **EnumWindows** esegue l'enumerazione di tutte le finestre esistenti nel computer, chiamando la funzione di callback per eseguire un'attività su ogni finestra. Per istruzioni e per un esempio, vedere [Procedura: Implementare funzioni di callback](../../../docs/framework/interop/how-to-implement-callback-functions.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Implementare funzioni di callback](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 [Chiamata a una funzione di DLL](../../../docs/framework/interop/calling-a-dll-function.md)
