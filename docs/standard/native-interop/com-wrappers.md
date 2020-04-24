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
ms.openlocfilehash: d647a8cd73fa714e86454687a25501259f894f6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120716"
---
# <a name="com-wrappers"></a>Wrapper COM
COM è diverso dal modello a oggetti del runtime .NET per diversi aspetti importanti:  
  
- I client di oggetti COM devono gestire la durata di tali oggetti. Common Language Runtime gestisce la durata degli oggetti nel proprio ambiente.  
  
- I client di oggetti COM individuano la disponibilità di un servizio inviando una richiesta a un'interfaccia che offre il servizio in questione e, se il servizio è disponibile, ricevendo un puntatore all'interfaccia. I client di oggetti .NET possono ottenere una descrizione della funzionalità di un oggetto tramite reflection.  
  
- Gli oggetti .NET risiedono nella memoria gestita dall'ambiente di esecuzione del runtime .NET. L'ambiente di esecuzione può spostare gli oggetti in posizioni diverse all'interno della memoria per motivi di prestazioni e aggiornare tutti i riferimenti agli oggetti spostati. I client non gestiti, dopo aver ottenuto un puntatore a un oggetto, per rimanere nella stessa posizione si basano sull'oggetto stesso. Questi client non hanno alcun meccanismo di gestione di oggetti il cui percorso non sia fisso.  
  
 Per superare queste differenze, il runtime mette a disposizione classi wrapper. Tramite tali classi, sia ai client gestiti che ai client non gestiti le chiamate agli oggetti risultano eseguite all'interno dell'ambiente del client. Ogni volta che il client gestito chiama un metodo per un oggetto COM, il runtime crea un [Runtime Callable Wrapper](runtime-callable-wrapper.md) (RCW). Una delle funzioni degli RCW è nascondere le differenze tra meccanismi di riferimento gestiti e non gestiti. Il runtime crea anche un [COM Callable Wrapper](com-callable-wrapper.md) (CCW) per invertire il processo, consentendo a un client COM di chiamare facilmente un metodo per un oggetto .NET. Come illustrato nella figura seguente, la prospettiva del codice chiamante determina la classe wrapper creata dal runtime.  
  
 ![Cenni preliminari sul wrapper COM](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 Nella maggior parte dei casi, l'oggetto CCW o RCW standard generato dal runtime effettua un marshalling adeguato per le chiamate che superano il limite tra COM e il runtime .NET. Usando attributi personalizzati, è possibile, facoltativamente, impostare il modo in cui il runtime rappresenta il codice gestito e non gestito.  
  
## <a name="see-also"></a>Vedi anche

- [Interoperabilità COM avanzata in .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))
- [Runtime Callable Wrapper](runtime-callable-wrapper.md)
- [COM Callable Wrapper](com-callable-wrapper.md)
- [Personalizzazione di wrapper standard in .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))
- [Procedura: personalizzare Runtime Callable Wrapper in .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))
