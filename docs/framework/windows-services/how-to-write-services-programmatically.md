---
title: 'Procedura: Scrivere servizi a livello di codice'
description: Vedere come scrivere servizi a livello di codice configurando l'ereditarietà e altri elementi dell'infrastruttura.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
ms.openlocfilehash: 9693e3d387f38319519ab04211d8219fe1e5dda1
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925709"
---
# <a name="how-to-write-services-programmatically"></a>Procedura: Scrivere servizi a livello di codice
Se si sceglie di non usare il modello di progetto Servizio Windows, è possibile scrivere servizi personalizzati impostando manualmente l'ereditarietà e altri elementi di infrastruttura. Quando si crea un servizio a livello di codice, è necessario eseguire diversi passaggi che altrimenti vengono gestiti automaticamente dal modello:  
  
- È necessario impostare la classe del servizio in modo che erediti dalla classe <xref:System.ServiceProcess.ServiceBase>.  
  
- È necessario creare un metodo `Main` per il progetto del servizio che definisce i servizi da eseguire e chiama il metodo <xref:System.ServiceProcess.ServiceBase.Run%2A> su di essi.  
  
- È necessario eseguire l'override delle procedure <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> e scrivere l'eventuale codice che si vuole eseguire con tali procedure.  
  
### <a name="to-write-a-service-programmatically"></a>Per scrivere un servizio a livello di codice  
  
1. Creare un progetto vuoto e creare un riferimento agli spazi dei nomi necessari seguendo questa procedura:  
  
    1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** e scegliere **Aggiungi riferimento**.  
  
    2. Nella scheda **.NET Framework** scorrere fino a **System.dll** e fare clic su **Seleziona**.  
  
    3. Scorrere fino a **System.ServiceProcess.dll** e fare clic su **Seleziona**.  
  
    4. Fare clic su **OK**.  
  
2. Aggiungere una classe e configurarla in modo che erediti da <xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3. Aggiungere il codice seguente per configurare la classe di servizio:  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4. Creare un metodo `Main` per la classe e usarlo per definire il servizio che verrà incluso nella classe. `userService1` è il nome della classe:  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5. Eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e definire l'elaborazione da eseguire eventualmente all'avvio del servizio.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6. Eseguire l'override di qualsiasi altro metodo per cui si vuole definire un'elaborazione personalizzata e scrivere il codice per determinare le azioni che il servizio deve eseguire in ogni caso.  
  
7. Aggiungere i programmi di installazione necessari per l'applicazione di servizio. Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).  
  
8. Compilare il progetto scegliendo **Compila soluzione** dal menu **Compila**.  
  
    > [!NOTE]
    > Non è possibile eseguire un progetto di servizio premendo F5.  
  
9. Creare un progetto per il programma di installazione e le azioni personalizzate per installare il servizio. Per un esempio, vedere [Procedura dettagliata: Creazione di un'applicazione di servizio Windows in Progettazione componenti](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Installare il servizio. Per altre informazioni, vedere [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle applicazioni di servizio Windows](introduction-to-windows-service-applications.md)
- [Procedura: Creare servizi Windows](how-to-create-windows-services.md)
- [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md)
- [Procedura: Registrare informazioni sui servizi](how-to-log-information-about-services.md)
- [Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
