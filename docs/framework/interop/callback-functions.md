---
title: Funzioni di callback
description: Leggere le informazioni sulle funzioni di callback, ovvero codice con un'applicazione gestita che consente a una funzione di DLL non gestita di completare un'attività.
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
ms.openlocfilehash: e28756b5ed935aff83363b38d6f33982e87718b2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621717"
---
# <a name="callback-functions"></a>Funzioni di callback
Una funzione di callback è il codice di un'applicazione gestita che agevola una funzione di DLL non gestita nel completamento di un'attività. Le chiamate a una funzione di callback passano indirettamente da un'applicazione gestita a una funzione di DLL, per poi tornare nuovamente all'implementazione gestita. Alcune delle numerose funzioni di DLL chiamate tramite platform invoke richiedono, per essere eseguite in modo corretto, una funzione di callback nel codice gestito.  
  
 Nella maggior parte dei casi, per chiamare una funzione di DLL dal codice gestito, si crea e si usa una definizione gestita della funzione. Il processo è semplice.  
  
 L'utilizzo di una funzione di DLL che richiede una funzione di callback prevede alcuni passaggi aggiuntivi. In primo luogo è necessario determinare se la funzione richiede un callback controllando la documentazione relativa alla funzione. Successivamente occorre creare la funzione di callback nell'applicazione gestita. Infine si chiama la funzione di DLL passandole come argomento un puntatore alla funzione di callback.

 La figura seguente presenta una riepilogo della funzione di callback e dei passaggi di implementazione:  
  
 ![Diagramma che illustra il processo di callback di platform invoke.](./media/callback-functions/platform-invoke-callback-process.gif)  
  
 Le funzioni di callback sono ideali per i casi in cui un'attività viene eseguita ripetutamente. Un altro utilizzo comune è quello con le funzioni di enumerazione, ad esempio **EnumFontFamilies**, **EnumPrinters** e **EnumWindows** nell'API Windows. La funzione **EnumWindows** esegue l'enumerazione di tutte le finestre esistenti nel computer, chiamando la funzione di callback per eseguire un'attività su ogni finestra. Per istruzioni e per un esempio, vedere [Procedura: Implementare funzioni di callback](how-to-implement-callback-functions.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Implementare funzioni di callback](how-to-implement-callback-functions.md)
- [Chiamata a una funzione di DLL](calling-a-dll-function.md)
