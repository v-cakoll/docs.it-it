---
title: 'Procedura: scrivere servizi a livello di codice'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 1721417b8d1fc799e6af5d09762ee852d9fbfb03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-services-programmatically"></a>Procedura: scrivere servizi a livello di codice
Se si sceglie di non utilizzare il modello di progetto di servizio Windows, è possibile scrivere i propri servizi impostando l'ereditarietà e altri elementi dell'infrastruttura manualmente. Quando si crea un servizio a livello di codice, è necessario eseguire diversi passaggi gestiti automaticamente il modello:  
  
-   È necessario impostare la classe di servizio da cui ereditare la <xref:System.ServiceProcess.ServiceBase> classe.  
  
-   È necessario creare un `Main` metodo per il progetto di servizio che definisce i servizi da eseguire e chiama il <xref:System.ServiceProcess.ServiceBase.Run%2A> metodo su di essi.  
  
-   È necessario eseguire l'override di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedure e scrivere il codice desiderato per l'esecuzione.  
  
### <a name="to-write-a-service-programmatically"></a>Scrivere un servizio a livello di codice  
  
1.  Creare un progetto vuoto e creare un riferimento agli spazi dei nomi necessari attenendosi alla procedura seguente:  
  
    1.  In **Esplora**, fare doppio clic su di **riferimenti** nodo e fare clic su **Aggiungi riferimento**.  
  
    2.  Nel **.NET Framework** scheda, scorrere fino a **System.dll** e fare clic su **selezionare**.  
  
    3.  Scorrere fino a **System.ServiceProcess.dll** e fare clic su **selezionare**.  
  
    4.  Fare clic su **OK**.  
  
2.  Aggiungere una classe e configurarlo in modo da ereditare <xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  Aggiungere il codice seguente per configurare la classe di servizio:  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  Creare un `Main` metodo per la classe e che consente di definire il servizio verrà contenuto la classe. `userService1` è il nome della classe:  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  Eseguire l'override di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (metodo) e definire i processi da eseguire quando viene avviato il servizio.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  Eseguire l'override di qualsiasi altro metodo che si desidera definire l'elaborazione per personalizzata e scrivere codice per determinare le azioni che il servizio deve intraprendere in ogni caso.  
  
7.  Aggiungere i programmi di installazione necessari per l'applicazione di servizio. Per ulteriori informazioni, vedere [procedura: aggiungere programmi di installazione per l'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
8.  Compilare il progetto selezionando **Compila soluzione** dal **compilare** menu.  
  
    > [!NOTE]
    >  Non è possibile eseguire un progetto di servizio premendo F5.  
  
9. Creare un progetto di installazione e le azioni personalizzate per installare il servizio. Per un esempio, vedere [procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Installare il servizio. Per altre informazioni, vedere [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Procedura: creare servizi Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Procedura: aggiungere programmi di installazione all'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Procedura: registrare informazioni sui servizi](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [Procedura dettagliata: Creazione di un'applicazione di servizio Windows in Progettazione componenti](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
