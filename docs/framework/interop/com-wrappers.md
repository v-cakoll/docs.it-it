---
title: Wrapper COM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0c83cae510d695dc05b2cc6a71fdef7b5244a2ea
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="com-wrappers"></a>Wrapper COM
COM è diverso dal modello a oggetti .NET Framework per diversi aspetti importanti:  
  
-   I client di oggetti COM devono gestire la durata di tali oggetti. Common Language Runtime gestisce la durata degli oggetti nel proprio ambiente.  
  
-   I client di oggetti COM individuano la disponibilità di un servizio inviando una richiesta a un'interfaccia che offre il servizio in questione e, se il servizio è disponibile, ricevendo un puntatore all'interfaccia. I client di oggetti .NET possono ottenere una descrizione della funzionalità di un oggetto tramite reflection.  
  
-   Gli oggetti .NET risiedono nella memoria gestita dall'ambiente di esecuzione di .NET Framework. L'ambiente di esecuzione può spostare gli oggetti in posizioni diverse all'interno della memoria per motivi di prestazioni e aggiornare tutti i riferimenti agli oggetti spostati. I client non gestiti, dopo aver ottenuto un puntatore a un oggetto, per rimanere nella stessa posizione si basano sull'oggetto stesso. Questi client non hanno alcun meccanismo di gestione di oggetti il cui percorso non sia fisso.  
  
 Per superare queste differenze, il runtime mette a disposizione classi wrapper. Tramite tali classi, sia ai client gestiti che ai client non gestiti le chiamate agli oggetti risultano eseguite all'interno dell'ambiente del client. Ogni volta che il client gestito chiama un metodo per un oggetto COM, il runtime crea un [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW). Una delle funzioni degli RCW è nascondere le differenze tra meccanismi di riferimento gestiti e non gestiti. Il runtime crea anche un [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) (CCW) per invertire il processo, consentendo a un client COM di chiamare facilmente un metodo per un oggetto .NET. Come illustrato nella figura seguente, la prospettiva del codice chiamante determina la classe wrapper creata dal runtime.  
  
 ![Cenni preliminari sul wrapper COM](../../../docs/framework/interop/media/bidirectional.gif "bidirezionale")  
Cenni preliminari sul wrapper COM  
  
 Nella maggior parte dei casi, l'RCW o il CCW generato dal runtime effettua un marshalling adeguato per le chiamate che superano il limite tra COM e .NET Framework. Usando attributi personalizzati, è possibile, facoltativamente, impostare il modo in cui il runtime rappresenta il codice gestito e non gestito.  
  
## <a name="see-also"></a>Vedere anche  
 [Interoperabilità COM avanzata](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md)   
 [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md)   
 [Personalizzazione di wrapper standard](http://msdn.microsoft.com/en-us/c40d089b-6a3c-41b5-a20d-d760c215e49d)   
 [Procedura: Personalizzare Runtime Callable Wrapper](http://msdn.microsoft.com/en-us/4a4bb3da-4d60-4517-99f2-78d46a681732)

