---
title: Attivazione XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f513b10c84de968d5a18b800037b512aad90399e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-activation"></a>Attivazione XAML
In questo esempio viene illustrato come ospitare un flusso di lavoro dichiarativo in IIS. L'esempio è un flusso di lavoro di base chiamato `EchoService` che ha un'operazione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, visitare la pagina di download per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire la soluzione XAMLActivation.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare la soluzione premendo **F5**.  
  
3.  Eseguire WcfTestClient.exe. Da un prompt dei comandi digitare il comando seguente:  
  
    1.  cd %SystemDrive%\Programmi\Microsoft Visual Studio 10.0\Common7\IDE\  
  
    2.  Eseguire WcfTestClient.exe.  
  
4.  Impostare l'indirizzo del servizio su WcfTestClient.exe premendo CTRL+MAIUSC+A e impostando l'indirizzo del servizio su http://localhost:56133/Service.xamlx.  
  
5.  Eseguire l'operazione echo per testare il servizio.  
  
6.  Distribuire il servizio in IIS usando DeployToIIS.Bat in un prompt dei comandi con privilegi di amministratore.  
  
7.  Aggiornare l'indirizzo del servizio nel client modificandolo in http://localhost/XAMLActivation/Service.xamlx e testare di nuovo il servizio usando WcfTestClient.exe.
