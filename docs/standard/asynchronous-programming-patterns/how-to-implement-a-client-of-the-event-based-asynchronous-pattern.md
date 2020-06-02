---
title: 'Procedura: implementare un client del modello asincrono basato su eventi'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: f834ce4a0ec2208eee80ce8c3ffebfa6fdeeb5b1
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289408"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>Procedura: implementare un client del modello asincrono basato su eventi
L'esempio di codice seguente mostra come usare un componente che aderisce a quanto indicato in [Panoramica del modello asincrono basato su eventi](event-based-asynchronous-pattern-overview.md). Il form per questo esempio usa il componente `PrimeNumberCalculator` descritto in [Procedura: Implementare un componente che supporta il modello asincrono basato su eventi](component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Quando si esegue un progetto che usa questo esempio, viene visualizzato un form "Calcolatrice di numeri primi" con una griglia e due pulsanti: **Avvia nuova attività** e **Annulla**. È possibile fare clic sul pulsante **Avvia nuova attività** più volte in successione. Per ogni clic, un'operazione asincrona avvierà un calcolo per determinare se un numero di test generato in modo casuale è un numero primo. Il form visualizzerà periodicamente l'avanzamento e i risultati incrementali. A ogni operazione viene assegnato un ID attività univoco. Il risultato del calcolo viene visualizzato nella colonna **Risultato**. Se il numero di test non è un numero primo, viene contrassegnato come **Composito** e ne viene visualizzato il primo divisore.  
  
 Qualsiasi operazione in sospeso può essere annullata con il pulsante **Annulla**. È possibile eseguire più selezioni.  
  
> [!NOTE]
> La maggior parte dei numeri non sarà un numero primo. Se non è stato trovato alcun numero primo dopo il completamento di diverse operazioni, avviare semplicemente altre attività e si finirà certamente per trovare alcuni numeri primi.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
