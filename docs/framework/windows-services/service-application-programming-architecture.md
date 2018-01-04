---
title: Architettura di programmazione delle applicazioni di servizio
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
- ServiceController components, programming architecture
- ServiceBase class, service states
- Windows Service applications, code model
- services, programming architecture
- ServiceController class
- services, states
- ServiceProcessInstaller class, service application code model
- Windows Service applications, states
ms.assetid: 83230026-d068-4174-97ff-e264c896eb2f
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 2d44ee323040346437261b51fddb707a30d1de6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="service-application-programming-architecture"></a>Architettura di programmazione delle applicazioni di servizio
Le applicazioni di servizio Windows sono basate su una classe che eredita dalla <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> classe. Eseguire l'override di metodi da questa classe e definire le funzionalità per utilizzarli per determinare il comportamento del servizio.  
  
 Le classi principali coinvolte nella creazione del servizio sono:  
  
-   <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>-Si esegue l'override di metodi di <xref:System.ServiceProcess.ServiceBase> classe durante la creazione di un servizio e definire il codice per determinare il funzionamento del servizio in questa classe ereditata.  
  
-   <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType>e <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> : consentono di installare e disinstallare il servizio.  
  
 Inoltre, una classe denominata <xref:System.ServiceProcess.ServiceController> può essere utilizzato per modificare il servizio. Questa classe non viene eseguita la creazione di un servizio, ma può essere utilizzata per avviare e arrestare il servizio, passare a esso i comandi e restituire una serie di enumerazioni.  
  
## <a name="defining-your-services-behavior"></a>La definizione del comportamento del servizio  
 Nella classe del servizio, si esegue l'override delle funzioni della classe base che determinano ciò che accade quando lo stato del servizio viene modificato in Gestione controllo servizi. La <xref:System.ServiceProcess.ServiceBase> classe espone i metodi seguenti, che è possibile eseguire l'override per aggiungere un comportamento personalizzato.  
  
|Metodo|Eseguire l'override per|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Indicare quali azioni devono essere eseguite quando viene avviato il servizio. È necessario scrivere codice in questa procedura per il servizio eseguire operazioni utili.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Indicare l'azione da eseguire quando il servizio viene sospesa.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Indicare l'azione da eseguire quando si arresta il servizio.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Indicare l'azione da intraprendere quando il servizio riprende il normale funzionamento dopo essere stato sospeso.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Indicare l'azione da eseguire prima il sistema in corso l'arresto, se il servizio è in esecuzione in quel momento.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Indicare l'azione da eseguire quando il servizio riceve un comando personalizzato. Per ulteriori informazioni sui comandi personalizzati, vedere MSDN online.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Indicare come il servizio deve rispondere quando viene ricevuto un evento di risparmio energia, ad esempio una batteria in esaurimento o sospeso.|  
  
> [!NOTE]
>  Questi metodi rappresentano gli Stati che il servizio viene convogliato attraverso il ciclo di vita; le transizioni del servizio da uno stato al successivo. Ad esempio, non si otterranno mai il servizio per rispondere a un <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> comando prima di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> è stato chiamato.  
  
 Esistono diverse altre proprietà e metodi di interesse. Sono inclusi:  
  
-   Il <xref:System.ServiceProcess.ServiceBase.Run%2A> metodo la <xref:System.ServiceProcess.ServiceBase> classe. Questo è il punto di ingresso principale per il servizio. Quando si crea un servizio utilizzando il modello di servizio Windows, il codice viene inserito all'interno dell'applicazione `Main` metodo per eseguire il servizio. Questo codice simile al seguente:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    >  Negli esempi viene utilizzata una matrice di tipo <xref:System.ServiceProcess.ServiceBase>, in cui ogni servizio contiene l'applicazione può essere aggiunto e quindi tutti i servizi possono essere eseguiti insieme. Se si crea solo un singolo servizio, tuttavia, è possibile scegliere di non utilizzare la matrice e, dichiarare un nuovo oggetto che eredita da <xref:System.ServiceProcess.ServiceBase> e quindi eseguirlo. Per un esempio, vedere [procedura: scrivere servizi a livello di codice](../../../docs/framework/windows-services/how-to-write-services-programmatically.md).  
  
-   Una serie di proprietà di <xref:System.ServiceProcess.ServiceBase> classe. Consentono di determinare quali metodi possono essere chiamati sul servizio. Ad esempio, quando il <xref:System.ServiceProcess.ServiceBase.CanStop%2A> è impostata su `true`, <xref:System.ServiceProcess.ServiceBase.OnStop%2A> metodo sul servizio può essere chiamato. Quando il <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> è impostata su `true`, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> e <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> metodi possono essere chiamati. Quando si imposta una di queste proprietà per `true`, è quindi necessario eseguire l'override e definire operazioni di elaborazione per i metodi associati.  
  
    > [!NOTE]
    >  Il servizio deve eseguire l'override almeno <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> siano utili.  
  
 È inoltre possibile utilizzare un componente denominato il <xref:System.ServiceProcess.ServiceController> per comunicare con e controllare il comportamento di un servizio esistente.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione alle applicazioni di servizio Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Procedura: creare servizi Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)
