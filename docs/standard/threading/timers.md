---
title: Timer
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 478484651bf839f842148f0b4164c9387db3b98a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584957"
---
# <a name="timers"></a>Timer
I timer sono oggetti leggeri che consentono di specificare un delegato da chiamare a un'ora specificata. Un thread nel pool di thread esegue l'operazione di attesa.  
  
 L'uso della classe <xref:System.Threading.Timer?displayProperty=nameWithType> è semplice. Si crea un **timer**, passando un delegato <xref:System.Threading.TimerCallback> al metodo di callback, un oggetto che rappresenta lo stato che verrà passato al callback, un'ora di generazione iniziale e un'ora che rappresenta il periodo compreso tra le chiamate di callback. Per annullare un timer in sospeso, chiamare la funzione **Timer.Dispose**.  
  
> [!NOTE]
>  Esistono altre due classi di timer. La classe <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> è un controllo che funziona con finestre di progettazione visiva e deve essere usata nei contesti dell'interfaccia utente; genera eventi nel thread dell'interfaccia utente. La classe <xref:System.Timers.Timer?displayProperty=nameWithType> deriva da <xref:System.ComponentModel.Component> e pertanto può essere usata con le finestre di progettazione visiva; anch'essa genera eventi, ma li genera in un thread <xref:System.Threading.ThreadPool>. La classe <xref:System.Threading.Timer?displayProperty=nameWithType> crea i callback in un thread <xref:System.Threading.ThreadPool> senza usare il modello di eventi. A differenza di altri timer, fornisce inoltre un oggetto di stato al metodo di callback. È estremamente semplice.  
  
 Nell'esempio seguente viene avviato un timer che inizia dopo un secondo (1000 millisecondi) e segna ogni secondo finché non si preme il tasto **Invio**. La variabile contenente il riferimento al timer è un campo a livello di classe, per assicurarsi che il timer non venga sottoposto al processo di garbage collection mentre è ancora in esecuzione. Per altre informazioni sul garbage collection, vedere <xref:System.GC.KeepAlive%2A>.  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Timer>  
 [Oggetti e funzionalità del threading](../../../docs/standard/threading/threading-objects-and-features.md)
