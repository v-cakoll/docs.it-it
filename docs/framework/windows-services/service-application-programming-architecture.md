---
title: Architettura di programmazione delle applicazioni di servizio
description: Informazioni sull'architettura di programmazione delle applicazioni di servizio. Le applicazioni di servizio Windows sono basate su una classe che eredita da System. ServiceProcess. ServiceBase.
ms.date: 03/30/2017
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
author: ghogen
ms.openlocfilehash: c59ccc5a8b2f11fda9c4734487092c1aabb74908
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925579"
---
# <a name="service-application-programming-architecture"></a>Architettura di programmazione delle applicazioni di servizio
Le applicazioni di servizio Windows sono basate su una classe che eredita dalla classe <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>. Eseguire l'override dei metodi da questa classe e definirne le funzionalità per determinare il comportamento del servizio.  
  
 Le classi principali coinvolte nella creazione del servizio sono:  
  
- <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> - Si esegue l'override dei metodi dalla classe <xref:System.ServiceProcess.ServiceBase> durante la creazione di un servizio e si definisce il codice per determinare il funzionamento del servizio in questa classe ereditata.  
  
- <xref:System.ServiceProcess.ServiceProcessInstaller?displayProperty=nameWithType> e <xref:System.ServiceProcess.ServiceInstaller?displayProperty=nameWithType> - Si usano queste classi per installare e disinstallare il servizio.  
  
 Inoltre, una classe denominata <xref:System.ServiceProcess.ServiceController> può essere usata per modificare il servizio stesso. Questa classe non è coinvolta nella creazione di un servizio, ma può essere usata per avviare e arrestare il servizio, passare comandi al servizio e restituire una serie di enumerazioni.  
  
## <a name="defining-your-services-behavior"></a>Definizione del comportamento del servizio  
 Nella classe del servizio si esegue l'override delle funzioni della classe di base, che determinano ciò che accade quando lo stato del servizio cambia in Gestione controllo servizi. La classe <xref:System.ServiceProcess.ServiceBase> espone i metodi seguenti, di cui è possibile eseguire l'override per aggiungere comportamenti personalizzati.  
  
|Metodo|Override per|  
|------------|-----------------|  
|<xref:System.ServiceProcess.ServiceBase.OnStart%2A>|Indicare quali azioni devono essere eseguite all'avvio del servizio. È necessario scrivere codice in questa procedura per fare eseguire operazioni utili al servizio.|  
|<xref:System.ServiceProcess.ServiceBase.OnPause%2A>|Indicare le azioni da eseguire quando il servizio viene sospeso.|  
|<xref:System.ServiceProcess.ServiceBase.OnStop%2A>|Indicare le azioni da eseguire in caso di arresto del servizio.|  
|<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>|Indicare le azioni da eseguire quando il servizio riprende il normale funzionamento dopo una sospensione.|  
|<xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>|Indicare le azioni da eseguire appena prima della chiusura del sistema, se il servizio è sempre in esecuzione.|  
|<xref:System.ServiceProcess.ServiceBase.OnCustomCommand%2A>|Indicare le azioni da eseguire quando il servizio riceve un comando personalizzato. Per altre informazioni sui comandi personalizzati, vedere MSDN online.|  
|<xref:System.ServiceProcess.ServiceBase.OnPowerEvent%2A>|Indicare come deve rispondere il servizio quando viene ricevuto un evento di risparmio energia, ad esempio la batteria in esaurimento o la sospensione del sistema.|  
  
> [!NOTE]
> Questi metodi rappresentano gli stati che assume il servizio durante il ciclo di vita. Il servizio passa da uno stato al successivo. Ad esempio, il servizio non risponderà mai a un comando <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> prima della chiamata di <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.  
  
 Esistono vari altri metodi e proprietà interessanti. Queste includono:  
  
- Metodo <xref:System.ServiceProcess.ServiceBase.Run%2A> nella classe <xref:System.ServiceProcess.ServiceBase>. Questo è il punto di ingresso principale per il servizio. Quando si crea un servizio usando il modello Servizio Windows, il codice viene inserito all'interno del metodo `Main` dell'applicazione per eseguire il servizio. Il codice è simile al seguente:  
  
     [!code-csharp[VbRadconService#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#6)]
     [!code-vb[VbRadconService#6](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#6)]  
  
    > [!NOTE]
    > Questi esempi usano una matrice di tipo <xref:System.ServiceProcess.ServiceBase>, in cui è possibile aggiungere ogni servizio contenuto dall'applicazione, in modo che tutti i servizi possano poi essere eseguiti insieme. Se si crea solo un singolo servizio, tuttavia, è possibile scegliere di non usare la matrice e dichiarare semplicemente un nuovo oggetto che eredita da <xref:System.ServiceProcess.ServiceBase> e quindi eseguirlo. Per un esempio, vedere [Procedura: Scrivere servizi a livello di codice](how-to-write-services-programmatically.md).  
  
- Una serie di proprietà per la classe <xref:System.ServiceProcess.ServiceBase>. Queste proprietà determinano i metodi che possono essere chiamati per il servizio. Ad esempio, quando la proprietà <xref:System.ServiceProcess.ServiceBase.CanStop%2A> è impostata su `true`, è possibile chiamare il metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> sul servizio. Quando la proprietà <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> è impostata su `true`, è possibile chiamare i metodi <xref:System.ServiceProcess.ServiceBase.OnPause%2A> e <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>. Quando si imposta una di queste proprietà su `true`, è quindi necessario eseguire l'override e definire l'elaborazione per i metodi associati.  
  
    > [!NOTE]
    > Il servizio deve eseguire l'override almeno di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> per essere utile.  
  
 È anche possibile usare un componente denominato <xref:System.ServiceProcess.ServiceController> per comunicare con un servizio esistente e controllarne il comportamento.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle applicazioni di servizio Windows](introduction-to-windows-service-applications.md)
- [Procedura: Creare servizi Windows](how-to-create-windows-services.md)
