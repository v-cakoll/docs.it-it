---
title: Wrapper COM
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38031509b999662c86657f0f5cdc7202de65c194
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607199"
---
# <a name="com-wrappers"></a>Wrapper COM
COM è diverso dal modello a oggetti .NET Framework per diversi aspetti importanti:  
  
-   I client di oggetti COM devono gestire la durata di tali oggetti. Common Language Runtime gestisce la durata degli oggetti nel proprio ambiente.  
  
-   I client di oggetti COM individuano la disponibilità di un servizio inviando una richiesta a un'interfaccia che offre il servizio in questione e, se il servizio è disponibile, ricevendo un puntatore all'interfaccia. I client di oggetti .NET possono ottenere una descrizione della funzionalità di un oggetto tramite reflection.  
  
-   Gli oggetti .NET risiedono nella memoria gestita dall'ambiente di esecuzione di .NET Framework. L'ambiente di esecuzione può spostare gli oggetti in posizioni diverse all'interno della memoria per motivi di prestazioni e aggiornare tutti i riferimenti agli oggetti spostati. I client non gestiti, dopo aver ottenuto un puntatore a un oggetto, per rimanere nella stessa posizione si basano sull'oggetto stesso. Questi client non hanno alcun meccanismo di gestione di oggetti il cui percorso non sia fisso.  
  
 Per superare queste differenze, il runtime mette a disposizione classi wrapper. Tramite tali classi, sia ai client gestiti che ai client non gestiti le chiamate agli oggetti risultano eseguite all'interno dell'ambiente del client. Ogni volta che il client gestito chiama un metodo per un oggetto COM, il runtime crea un [Runtime Callable Wrapper](runtime-callable-wrapper.md) (RCW). Una delle funzioni degli RCW è nascondere le differenze tra meccanismi di riferimento gestiti e non gestiti. Il runtime crea anche un [COM Callable Wrapper](com-callable-wrapper.md) (CCW) per invertire il processo, consentendo a un client COM di chiamare facilmente un metodo per un oggetto .NET. Come illustrato nella figura seguente, la prospettiva del codice chiamante determina la classe wrapper creata dal runtime.  
  
 ![Cenni preliminari sul wrapper COM](media/bidirectional.gif "bidirezionale")  
Cenni preliminari sul wrapper COM  
  
 Nella maggior parte dei casi, l'RCW o il CCW generato dal runtime effettua un marshalling adeguato per le chiamate che superano il limite tra COM e .NET Framework. Usando attributi personalizzati, è possibile, facoltativamente, impostare il modo in cui il runtime rappresenta il codice gestito e non gestito.  
  
## <a name="see-also"></a>Vedere anche
- [Interoperabilità COM avanzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))
- [Runtime Callable Wrapper](runtime-callable-wrapper.md)
- [COM Callable Wrapper](com-callable-wrapper.md)
- [Personalizzazione di wrapper standard](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100))
- [Procedura: Personalizzare Runtime Callable Wrapper](https://msdn.microsoft.com/library/4a4bb3da-4d60-4517-99f2-78d46a681732(v=vs.100))
