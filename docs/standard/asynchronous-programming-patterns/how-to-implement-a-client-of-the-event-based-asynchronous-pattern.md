---
title: 'Procedura: implementare un client del modello asincrono basato su eventi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>Procedura: implementare un client del modello asincrono basato su eventi
Esempio di codice seguente viene illustrato come utilizzare un componente che rispetti il [Panoramica del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md). Il form per questo esempio Usa il `PrimeNumberCalculator` componente descritto in [procedura: implementare un componente che supporta il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Quando si esegue un progetto che utilizza questo esempio, si verrà visualizzato un form "Calcolatrice di numeri primi" con una griglia e due pulsanti: **Avvia nuova attività** e **Annulla**. È possibile scegliere di **Avvia nuova attività** più volte in successione e per ogni clic, un'operazione asincrona inizierà a un calcolo per determinare se un numero di test in modo casuale generato è primo. Il modulo verrà visualizzato periodicamente lo stato di avanzamento e risultati incrementali. Ogni operazione viene assegnato un ID attività univoco. Il risultato del calcolo viene visualizzato nel **risultato** colonna; se il numero di test non è primo, contrassegnato come **composito,** e viene visualizzato il relativo primo divisore.  
  
 Qualsiasi operazione in sospeso possono essere annullato con la **Annulla** pulsante. Può essere più selezioni.  
  
> [!NOTE]
>  Non è la maggior parte dei numeri primi. Se non è stato possibile trovare un numero primo dopo diverse operazioni completate, avviare semplicemente più attività e alla fine si troveranno alcuni numeri primi.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
