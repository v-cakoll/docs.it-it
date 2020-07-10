---
title: "Procedura: implementare un form che utilizza un'operazione in background"
description: Informazioni su come implementare un Windows Form che usa un'operazione in background in modo che un'operazione possa continuare a essere eseguita mentre un'altra operazione continua.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: 23bf4bc02fbf998d92dfce6d84e4e337cbefe7d9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174523"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a>Procedura: implementare un form che utilizza un'operazione in background
Nell'esempio di codice riportato di seguito viene creato un form che calcola numeri di Fibonacci. Il calcolo viene eseguito su un thread separato da quello dell'interfaccia utente, in modo che la risposta dell'interfaccia utente non venga ritardata dall'esecuzione del calcolo.  
  
 In Visual Studio è disponibile supporto completo per questa attività.  
  
 Vedere anche [Procedura dettagliata: implementazione di un modulo che usa un'operazione in background](walkthrough-implementing-a-form-that-uses-a-background-operation.md).  
  
## <a name="example"></a>Esempio  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
  
> [!CAUTION]
> L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi. Vedere [Procedure consigliate per l'uso del threading gestito](../../../standard/threading/managed-threading-best-practices.md) prima di implementare soluzioni che usano il multithreading.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [Cenni preliminari sul modello asincrono basato su eventi](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [Procedure consigliate per il threading gestito](../../../standard/threading/managed-threading-best-practices.md)
