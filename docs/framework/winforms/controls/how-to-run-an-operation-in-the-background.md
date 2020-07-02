---
title: "Procedura: eseguire un'operazione in background"
description: Informazioni su come usare la classe BackgroundWorker per eseguire un'operazione di Windows Forms dispendiosa in termini di tempo in background.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 6b2a97f5acf1e906dfe141aee62e99a4e50dca9f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621574"
---
# <a name="how-to-run-an-operation-in-the-background"></a>Procedura: eseguire un'operazione in background
Se l'esecuzione di un'operazione richiede molto tempo e si vogliono evitare ritardi nella risposta dell'interfaccia utente, è possibile usare la classe <xref:System.ComponentModel.BackgroundWorker> per eseguire l'operazione in un altro thread.  
  
 L'esempio di codice seguente illustra come eseguire in background un'operazione che richiede molto tempo. Nel form sono presenti i pulsanti **Avvia** e **Annulla**. Fare clic sul pulsante **Avvia** per eseguire un'operazione asincrona. Fare clic sul pulsante **Annulla** per interrompere l'esecuzione dell'operazione asincrona. Il risultato di ciascuna operazione viene visualizzato in una finestra di messaggio <xref:System.Windows.Forms.MessageBox>.  
  
 In Visual Studio è disponibile supporto completo per questa attività.  
  
 Vedere anche [Procedura dettagliata: Esecuzione di un'operazione in background](walkthrough-running-an-operation-in-the-background.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [Procedura: implementare un form che utilizza un'operazione in background](how-to-implement-a-form-that-uses-a-background-operation.md)
- [Componente BackgroundWorker](backgroundworker-component.md)
